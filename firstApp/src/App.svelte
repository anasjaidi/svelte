<script>
  let counter = 0;

  const incButtonClickHandler = e => {
    console.log(e);
    counter++;
  }

</script>

<main>
  <div>
    <p>counter: {counter}</p>
    <button on:click={incButtonClickHandler}>inc</button>
  </div>
</main>