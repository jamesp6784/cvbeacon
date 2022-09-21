<script lang="ts">
    import JobListing from "./JobListing.svelte";
    import JobDetails from "./JobDetails.svelte";

    import rocketLabIcon from "../../assets/rocket_lab.png";
    import sharesiesIcon from "../../assets/sharesies.png";

    let selected;

    // function listingClick(event) {
    //     event.target.
    // }
</script>

<div class="container">
    <div class="list">
        <JobListing icon={rocketLabIcon} on:click={listingClick}/>
        <JobListing icon={sharesiesIcon}/>
        <JobListing />
        <JobListing />
        <JobListing />
        <JobListing />
        <JobListing />
    </div>
    <div class="details">
        <JobDetails />
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
