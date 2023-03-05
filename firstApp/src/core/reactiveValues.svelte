
<script>
    /**
     * @desc In Svelte, a reactive value is any value used in the component's template that can change over time,
     *      triggering automatic updates to the view.
     * @methods they are three methods to create reactive values
     *
     * @let Declaring a variable with the let keyword in a Svelte component's script section creates a reactive,
     *      value that triggers a re-render of the component when changed, but it need to be used in the view template.
     *
     * @$: Using the $: syntax in a Svelte component creates a reactive expression that is automatically re-evaluated,
     *      and updates the view whenever any of its dependent reactive values change.
     *
     * @writable A writable store is a reactive value in Svelte that allows for manual updates to its value,
     *           created with the writable function from the svelte/store module. Changes to the store's value,
     *           trigger updates to the view.
     * */
    import { writable } from 'svelte/store';
    const counter = writable(0);

    function handleClick() {
        counter.update(n => n + 1);
    }
    let count = 0;
    $: doubledCount = count * 2;
    const incCount = () => {
        count++
    }
</script>


<main>
    <div class="let">
        <p>The count is {count}</p>
        <button on:click={incCount}>inc count</button>
    </div>
    <div class="$:">
        <p>The count is {count}, and its double is {doubledCount}</p>
    </div>
    <div class="writable">
        <button on:click={handleClick}>Click me</button>
        <p>The count is {$counter}</p>
    </div>
</main>

<style>

</style>