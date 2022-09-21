<script lang="ts">
    import JobHeader from "./JobHeader.svelte";

    let listing;

    export { listing };
</script>

<div class="outer">
    <JobHeader {listing} small={false} />

    <div class="body">
        {#each listing.body as bodyObject}
            {#if bodyObject.type === "header"}
                <h3>{bodyObject.content}</h3>
            {:else if bodyObject.type === "list"}
                {#each bodyObject.items as listItem}
                    <p>●&nbsp;&nbsp;{listItem}</p>
                {/each}
            {:else}
                <p>{bodyObject.content}</p>
            {/if}
        {/each}
    </div>

    <div class="actions">
        <button>View details</button>
        <button class="apply">Apply</button>
    </div>
</div>

<style>
    .outer {
        width: 100%;
        background-color: #fff;
        padding: 12px 16px;
        border: 1px solid #ddd;
        margin-bottom: 16px;
    }

    img {
        width: 72px;
        margin-right: 8px;
    }

    span {
        vertical-align: top;
        display: inline-block;
    }

    .title {
        font-size: 18px;
        font-weight: 500;
    }

    .org {
        font-size: 15px;
    }

    .header {
        margin-bottom: 12px;
    }

    .body * {
        margin-top: 16px;
    }

    .actions {
        margin-top: 32px;
        float: right;
    }

    .actions button {
        padding: 8px 16px;
        border: 1px solid hsl(202, 60%, 40%);
        transition: background-color 0.2s ease, border 0.2s ease;
        cursor: pointer;
        font-size: 14px;
        color: hsl(202, 60%, 40%);
        box-sizing: content-box;
    }

    .actions button.apply {
        background-color: hsl(202, 60%, 40%);
        color: #fff;
    }

    .actions button:hover {
        background-color: hsl(202, 60%, 80%);
    }

    .actions button.apply:hover {
        background-color: hsl(202, 60%, 50%);
        border: 1px solid hsl(202, 60%, 50%);
    }
</style>
