<script>
    import Product from "./components/Product.svelte";
</script>

<Product productTitle="product 1" on:click={() => alert("yes")} deleteHandler="{() => console.log(123)}"></Product>

<style>

</style>
