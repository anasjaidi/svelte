<script>
    import Product from "./components/Product.svelte";
    import Modal from "./components/Modal.svelte";

    let agree = false
    let showModal = false
    let products = [
        {
            id: Math.random(),
            title: 'product 1',
            price: 12.99
        },
        {
            id: Math.random(),
            title: 'product 2',
            price: 15.99,
        },
    ]
    $:  productsFilltred = products.map(el => {
        return {title: el.title, price: el.price}
    })

</script>

{#if showModal}
<Modal on:cancel={() => showModal = false} on:close={() => showModal = false} let:didAgree={agree}>
    <h1 slot="header">Hi, There!</h1>
    <input type="email" name="email" id="email">
    <button slot="footer" on:click={() => showModal = false} disabled="{!agree}">confirm modal</button>
</Modal>
{/if}

{#each productsFilltred as product}
    <Product
            {...product}
             on:add-element={(obj) => console.log(obj.detail.payload)}
            on:delete-element={(obj) => console.log(obj.detail.payload)}
    ></Product>
{/each}
<button on:click={() => showModal = true}>show Modal</button>
<style>

</style>
