<script>

  import ReactiveValues from "./core/reactiveValues.svelte";

  let counter = 0;
  let name = "";

  const incButtonClickHandler = e => {
    console.log(e);
    counter++;
  }

  const inputChangeHandler = e => {
    name = e.target.value
  }

  const resetButtonHandler = (e) => {
    e.preventDefault()
    name = "jaidi"
  }
</script>

<main>
  <div>
    <p style="font-size: {(counter > 16 ? counter : 16) + 'px'}">counter: {counter}</p>
    <button on:click={incButtonClickHandler}>inc</button>
  </div>
  <div>
    <p>Name: {name}</p>
    <form>
      <input type="text" on:input={inputChangeHandler} value={name}/>
      <input bind:value={name} />
      <button on:click={resetButtonHandler}>reset to jaidi</button>
    </form>
  </div>

  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <ReactiveValues />
</main>