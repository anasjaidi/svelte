<script>
    let name = ""
    $: showName = "Hi " + name
</script>

<main>
    <p>{showName}</p>
    <input  type="text" bind:value={name}/>
</main>

<style>

</style>
