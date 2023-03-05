<script>

    import ContactCard from "./components/ContactCard.svelte";

    let name = ""
    $: showName = "Hi " + name
</script>

<main>
    <p>{showName}</p>
    <input  type="text" bind:value={name}/>
</main>

<ContactCard></ContactCard>

<style>

</style>
