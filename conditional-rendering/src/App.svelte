<script>
  import ContactCard from "./ContactCard.svelte";

  let name = "Max";
  let title = "";
  let image = "";
  let description = "";
  let done = "empty"
  let createdContacts = []

  const addCartClickHandler = e => {
    if (name.trim().length > 0 && description.trim().length > 0 && image.trim().length > 0 && title.trim().length > 0) {
      done = "ready"
      createdContacts = [...createdContacts, {name, title, image, description, id: Math.random()}]
      return ;
    }
    done = "not-ready"
  }
</script>

<style>
  #form {
    width: 30rem;
    max-width: 100%;
    color: black;
  }
  input {
    color: #1a1a1a;
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



<!--{#if done === "ready"}-->
<!--      <ContactCard userName={name} jobTitle={title} {description} userImage={image} />-->
<!--{:else if done === "not-ready"}-->
<!--      <p>invalid</p>-->
<!--{:else}-->
<!--  <hr>-->
<!--{/if}-->

{#each createdContacts as contact, i (contact.id)}
  <h1>#{i}</h1>
  <ContactCard userName={contact.name} jobTitle={contact.title} description={contact.description} userImage={contact.image} />
{:else}
  <p>empty</p>
{/each}