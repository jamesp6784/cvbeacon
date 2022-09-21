<script lang="ts">
    import JobListing from "./JobListing.svelte";
    import JobDetails from "./JobDetails.svelte";
    import listings from "../../listings";

    let selected = listings[0];

    function listingClick(listing) {
        selected = listing;
    }
</script>

<div class="container">
    <div class="list">
        {#each listings as listing}
            <JobListing {listing} clickCallback={listingClick} />
        {/each}
    </div>
    <div class="details">
        <JobDetails listing={selected} />
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: row;
        align-items: stretch;
        width: 100%;
    }

    .list,
    .details {
        display: inline-block;
    }

    .list {
        width: 400px;
        margin-right: 24px;
    }

    .details {
        flex: 1;
    }
</style>
