<script lang="ts">
    import JobHeader from "./JobHeader.svelte";

    let listing;
    let small;
    let clickCallback;

    export { listing, small, clickCallback };

    function click() {
        clickCallback(listing);
    }
</script>

<div on:click={click}>
    <JobHeader {listing} {small} />
</div>

<style>
    div {
        background-color: #fff;
        padding: 12px 16px;
        border: 1px solid #ddd;
        margin-bottom: 16px;
        user-select: none;
        cursor: pointer;
    }
</style>
