
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

    let counter = 0;
</script>

<style>

</style>