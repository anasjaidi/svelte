<script>
    import Header from "./UI/Header.svelte";
    import MeetUpsItem from "./MeetUps/MeetUpItem.svelte";

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
    {#each meetups as meet (meet.id)}
        <MeetUpsItem
            title={meet.title}
            subtitle={meet.subtitle}
            imgUrl={meet.imageUrl}
            description={meet.description}
            contactAddress={meet.contactEmail}
            address={meet.address}
        ></MeetUpsItem>
    {/each}
</main>

<style>
    #main {
        margin-top: 5rem;
    }
</style>
