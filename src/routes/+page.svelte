<script lang="ts">
import Info from "./Info.svelte";
import ItemsList from "./ItemsList.svelte"; 

let selectedItem = { id: 0, name: "default item", price: 0 };


function itemClickedHandler(event) {
    console.log("page: ", event.detail.item);
    selectedItem = event.detail.item;
}
</script>

<h2>Info</h2>
<Info item={selectedItem} />

<hr>

<h2>ItemsList</h2>
<ItemsList on:itemClicked={itemClickedHandler}/>