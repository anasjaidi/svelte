<script>
  import ContactCard from "./ContactCard.svelte";

  let name = "Max";
  let title = "";
  let image = "";
  let description = "";
  let done = false

  const addCartClickHandler = e => {
    done = true
  }
</script>

<style>
  #form {
    width: 30rem;
    max-width: 100%;
  }
</style>

<div id="form">
  <div class="form-control">
    <label for="userName">User Name</label>
    <input type="text" bind:value={name} id="userName" />
  </div>
  <div class="form-control">
    <label for="jobTitle">Job Title</label>
    <input type="text" bind:value={title} id="jobTitle" />
  </div>
  <div class="form-control">
    <label for="image">Image URL</label>
    <input type="text" bind:value={image} id="image" />
  </div>
  <div class="form-control">
    <label for="desc">Description</label>
    <textarea rows="3" bind:value={description} id="desc" />
  </div>
</div>
<button on:click={addCartClickHandler}>submit</button>
{#if ((done && 1 )|| 0)}
<ContactCard userName={name} jobTitle={title} {description} userImage={image} />
  {:else if !done}
  <p>invalid</p>
  {/if}