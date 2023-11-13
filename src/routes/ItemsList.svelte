<script lang="ts">
import { createEventDispatcher } from "svelte";

const dispatch = createEventDispatcher();
let items = [
    { id: 1, name: "Item 1", price: 100 },
    { id: 2, name: "Item 2", price: 200 },
    { id: 3, name: "Item 3", price: 300 },
    { id: 4, name: "Item 4", price: 400 },
    { id: 5, name: "Item 5", price: 500 }
    ];



function itemClickHandler(event) {
    console.log("ItemsList: ", event.target.id);
    let selectedItem = items.find(item => item.id.toString() === event.target.id);

    dispatch("itemClicked", { item: selectedItem });
}
</script>

{#each items as item}
    <h1 id={item.id.toString()} on:click={itemClickHandler}>{item.id} {item.name} {item.price} </h1>
{/each}