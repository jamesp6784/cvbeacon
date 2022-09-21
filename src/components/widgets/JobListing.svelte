<script lang="ts">
    let listing;
    let clickCallback;

    export { listing, clickCallback };

    function click() {
        clickCallback(listing);
    }
</script>

<div on:click={click}>
    <img alt="{listing.org} icon" src={listing.icon} />
    <span>
        <p class="title">{listing.title}</p>
        <p class="org">{listing.org}</p>
    </span>
</div>

<style>
    div {
        width: 100%;
        background-color: #fff;
        padding: 12px 16px;
        border: 1px solid #ddd;
        margin-bottom: 16px;
        user-select: none;
        cursor: pointer;
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
</style>
