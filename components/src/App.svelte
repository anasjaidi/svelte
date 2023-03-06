<script>
    import Product from "./components/Product.svelte";
</script>

<Product productTitle="product 1" on:add-element={(obj) => console.log(obj.detail.payload)} on:delete-element={(obj) => console.log(obj.detail.payload)}></Product>

<style>

</style>
