<script lang="ts">
    import JobListing from "./JobListing.svelte";
    import JobDetails from "./JobDetails.svelte";
    import listings from "../../listings";
    import moreIcon from "../../assets/add.svg";
    import { currentPage } from "../../store";

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
        <div class="more" on:click={() => currentPage.set("jobs")}>
            <img alt="Plus" src={moreIcon} />
            <span>View more...</span>
        </div>
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

    .more {
        background-color: #fff;
        padding: 12px 16px;
        border: 1px solid #ccc;
        margin-bottom: 16px;
        user-select: none;
        cursor: pointer;
        transition: border 0.1s ease;
    }

    .more * {
        vertical-align: middle;
    }

    .more img {
        padding: 12px;
        margin-right: 8px;
    }

    .more span {
        font-size: 18px;
        font-weight: 500;
    }

    .more:hover {
        border: 1px solid hsl(202, 60%, 40%);
    }
</style>
