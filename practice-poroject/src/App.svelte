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
    let title;
    let subtitle;
    let address;
    let description;
    let contactEmail;
    let imgUrl;

    const submitClickHandler = e => {
        meetups = [...meetups, {
                id: Math.random(),
                title,
                subtitle,
                description,
                address,
                contactEmail,
                imageUrl: imgUrl
        }]
    }
</script>

<Header></Header>
<main id="main">
    <MeetupGrid {meetups} ></MeetupGrid>
    <form on:submit|preventDefault={submitClickHandler}>
        <div>
            <div class="form-control">
                <label for="title">title</label>
                <input type="text" id="title" bind:value={title}>
            </div>
            <div class="form-control">
                <label for="subtitle">subtitle</label>
                <input type="text" id="subtitle" bind:value={subtitle}>
            </div>
            <div class="form-control">
                <label for="addr">address</label>
                <input type="text" id="addr" bind:value={address}>
            </div>
            <div class="form-control">
                <label for="imgUrl">image url</label>
                <input type="text" id="imgUrl" bind:value={imgUrl}>
            </div>
            <div class="form-control">
                <label for="emailContact">contact email</label>
                <input type="text" id="emailContact" bind:value={contactEmail}>
            </div>
            <div class="form-control">
                <label for="desc">description</label>
                <textarea rows="3"  id="desc" bind:value={description}></textarea>
            </div>
            <button>add</button>
        </div>
    </form>
</main>

<style>
    #main {
        margin-top: 5rem;
    }
</style>
