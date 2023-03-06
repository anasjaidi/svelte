<script>
    import {createEventDispatcher} from "svelte";

    let agree = false;
    const dispatch = createEventDispatcher()
</script>

<div class="backdrop" on:click={() => {dispatch("cancel")}}></div>
<div class="modal">
    <header>
        <slot name="header"></slot>
    </header>
    <div class="content">
        <slot></slot>
    </div>
    <div>
        <button on:click={() => agree = true}>agree</button>
    </div>
    <footer>
        <slot name="footer" didAgree={agree}>
            <button on:click={() => {dispatch('close')}} disabled={!agree}>close</button>
        </slot>
    </footer>
</div>

<style>
    .backdrop {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        background: rgba(0, 0, 0, 0.75);
        z-index: 10;
    }

    .modal {
        padding: 1rem;
        position: fixed;
        top: 10vh;
        left: 10%;
        width: 80%;
        max-height: 80vh;
        background: white;
        border-radius: 5px;
        z-index: 100;
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
        overflow: scroll;
    }

</style>