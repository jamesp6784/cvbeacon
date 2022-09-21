<script lang="ts">
    import JobHeader from "./JobHeader.svelte";

    let listing;
    let clickCallback;

    export { listing, clickCallback };

    function click() {
        clickCallback(listing);
    }
</script>

<div on:click={click}>
    <JobHeader {listing} />
</div>

<style>
    div {
        background-color: #fff;
        padding: 12px 16px;
        border: 1px solid #ccc;
        margin-bottom: 16px;
        user-select: none;
        cursor: pointer;
        transition: border 0.1s ease;
    }

    div:hover {
        border: 1px solid hsl(202, 60%, 40%);
    }
</style>
