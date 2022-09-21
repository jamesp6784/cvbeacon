<script lang="ts">
    import JobListing from "./JobListing.svelte";
    import JobDetails from "./JobDetails.svelte";
</script>

<div class="container">
    <div class="list">
        <JobListing />
        <JobListing />
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
