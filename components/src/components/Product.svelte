<script>

    import {createEventDispatcher} from "svelte";

    const dispatcher = createEventDispatcher()
    export let productTitle;
</script>

<article>
    <h1>{productTitle}</h1>
    <button on:click={() => dispatcher("add-element", {payload: "Add"})}>add on card</button>
    <button on:click={() => dispatcher("delete-element", {payload: "Delete"})}>delete</button>
</article>

<style></style>