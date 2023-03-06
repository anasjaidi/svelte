<script>
    export let productTitle;
    export let deleteHandler;
</script>

<article>
    <h1>{productTitle}</h1>
    <button on:click>add on card</button>
    <button on:click={deleteHandler}>delete</button>
</article>

<style></style>