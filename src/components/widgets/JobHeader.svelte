<script lang="ts">
    let listing;
    let small;

    export { listing, small };
</script>

<div>
    <img alt="{listing.org} icon" src={listing.icon} />
    <span>
        <p class="title">{listing.title}</p>
        <p class="org">{listing.org}</p>
    </span>
</div>

<style>
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
