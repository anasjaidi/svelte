<script>
    import Header from "./UI/Header.svelte";
    import MeetupGrid from "./MeetUps/MeetupGrid.svelte";

    let meetups = [
        {
            id: "m1",
            title: "working with svelte",
            subtitle: "learning svelte in 12 hours",
            description: "learn how to build spa applications with svelte",
            address: "27th new york 2347",
            contactEmail: "anas.jaidi@icloud.com",
            imageUrl: ""
        },
        {
            id: "m2",
            title: "working with svelteKit",
            subtitle: "learning svelteKit in 12 hours",
            description: "learn how to build server-side-rendering applications with svelteKit",
            address: "27th new york 2347",
            contactEmail: "anas.jaidi@icloud.com",
            imageUrl: ""
        }
    ]
</script>

<Header></Header>
<main id="main">
    <MeetupGrid {meetups} ></MeetupGrid>
    <form>
        <div>
            <div class="form-control">
                <label for="title">title</label>
                <input type="text" id="title">
            </div>
            <div class="form-control">
                <label for="subtitle">subtitle</label>
                <input type="text" id="subtitle">
            </div>
            <div class="form-control">
                <label for="addr">address</label>
                <input type="text" id="addr">
            </div>
            <div class="form-control">
                <label for="imgUrl">image url</label>
                <input type="text" id="imgUrl">
            </div>
            <div class="form-control">
                <label for="emailContact">contact email</label>
                <input type="text" id="emailContact">
            </div>
            <div class="form-control">
                <label for="desc">description</label>
                <textarea  id="desc" />
            </div>
            <button on:click|preventDefault={submitClickHandler}>add</button>
        </div>
    </form>
</main>

<style>
    #main {
        margin-top: 5rem;
    }
</style>
