<script>

    import ContactCard from "./components/ContactCard.svelte";

    let name = ""
    let jobTitle = ""
    let desc = ""
    $: showName = "Hi " + name
</script>

<main>
    <p>{showName}</p>
    <br>
    full name: <input  type="text" bind:value={name}/>
    <br>
    job title: <input  type="text" bind:value={jobTitle}/>
    <br>
    desc: <input  type="text" bind:value={desc}/>
</main>

<ContactCard userName={name} jobTitle="{jobTitle}" description="{desc}"></ContactCard>

<style>

</style>
