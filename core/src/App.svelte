<script>

    import ContactCard from "./components/ContactCard.svelte";

    let name = ""
    let desc = ""
    let jobTitle = ""
    let imgLink = ""
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
    <br>
    image link: <input  type="text" bind:value={imgLink}/>
</main>

<ContactCard userName={name} jobTitle="{jobTitle}" description="{desc}" imgLink="{imgLink}"></ContactCard>

<style>

</style>
