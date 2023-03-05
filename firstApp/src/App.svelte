<script>
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
    <p>counter: {counter}</p>
    <button on:click={incButtonClickHandler}>inc</button>
  </div>
  <div>
    <p>Name: {name}</p>
    <form>
      <input type="text" on:input={inputChangeHandler} value={name}/>
      <button on:click={resetButtonHandler}>reset to jaidi</button>
    </form>
  </div>
</main>