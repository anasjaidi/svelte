<script>

    import {createEventDispatcher} from "svelte";

    const dispatcher = createEventDispatcher()
    export let title;
    export let price;

    export let bestSeller = false; // add default value to prevent un-passed props value warning
</script>

<article>
    <h1>{title}</h1>
    <h2>${price}</h2>
    {#if bestSeller === true}
        <b>BestSeller</b>
    {/if}
    <button on:click={() => dispatcher("add-element", {payload: "Add"})}>add on card</button>
    <button on:click={() => dispatcher("delete-element", {payload: "Delete"})}>delete</button>
</article>

<style></style>