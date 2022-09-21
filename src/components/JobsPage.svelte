<script lang="ts">
    import BasePage from "./BasePage.svelte";
    import JobListing from "./widgets/JobListing.svelte";
    import listings from "../listings";
    import JobDetails from "./widgets/JobDetails.svelte";

    let filter = "";

    $: filteredListings = listings.filter(
        (listing) =>
            listing.title.toLowerCase().includes(filter.toLowerCase()) ||
            listing.org.toLowerCase().includes(filter.toLowerCase())
    );

    let viewedListing;
</script>

<BasePage>
    {#if viewedListing}
        <button on:click={() => (viewedListing = null)}>Back</button>
        <JobDetails listing={viewedListing} />
    {:else}
        <h1>All Listings</h1>
        <input bind:value={filter} placeholder="Filter..." />
        {#each filteredListings as listing}
            <JobListing
                {listing}
                small={true}
                clickCallback={(l) => (viewedListing = l)}
            />
        {/each}
    {/if}
</BasePage>

<style>
    h1 {
        font-weight: 400;
        margin-bottom: 32px;
    }

    input {
        display: block;
        width: 100%;
        padding: 12px;
        font-size: 18px;
        background-color: #fff;
        border: 1px solid #ccc;
        margin-bottom: 24px;
        transition: border 0.1s ease;
    }

    input:focus {
        border: 1px solid hsl(202, 60%, 40%);
    }

    button {
        padding: 8px 16px;
        border: 1px solid #ccc;
        background-color: #fff;
        transition: background-color 0.2s ease, border 0.2s ease;
        cursor: pointer;
        font-size: 14px;
        box-sizing: content-box;
        margin-bottom: 12px;
        transition: border 0.1s ease;
    }

    button:hover {
        border: 1px solid hsl(202, 60%, 40%);
    }
</style>
