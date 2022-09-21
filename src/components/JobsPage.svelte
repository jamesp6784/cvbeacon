<script lang="ts">
    import BasePage from "./BasePage.svelte";
    import JobListing from "./widgets/JobListing.svelte";
    import listings from "../listings";

    let filter = "";

    $: filteredListings = listings.filter(
        (listing) =>
            listing.title.toLowerCase().includes(filter.toLowerCase()) ||
            listing.org.toLowerCase().includes(filter.toLowerCase())
    );
</script>

<BasePage>
    <h1>All Listings</h1>
    <input bind:value={filter} placeholder="Filter..." />
    {#each filteredListings as listing}
        <JobListing {listing} small={true} clickCallback={() => {}} />
    {/each}
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
    }
</style>
