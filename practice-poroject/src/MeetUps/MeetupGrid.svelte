<script>
    import MeetupItem from "./MeetupItem.svelte";

    export let meetups;
</script>

<section>
    {#each meetups as meet (meet.id)}
        <MeetupItem
                title={meet.title}
                subtitle={meet.subtitle}
                imgUrl={meet.imageUrl}
                description={meet.description}
                contactAddress={meet.contactEmail}
                address={meet.address}
        ></MeetupItem>
    {/each}
</section>


<style>
    section {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr;
        grid-gap: 1rem;
    }

    @media (min-width: 768px) {
        section {
            grid-template-columns: repeat(2, 1fr);
        }
    }
</style>