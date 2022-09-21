<script lang="ts">
    let listing;
    let small;

    export { listing, small };
</script>

<div>
    <img alt="{listing.org} icon" src={listing.icon} />
    <span>
        <p class="title">{listing.title}</p>
        <p class="subtitle">{listing.org} · {listing.type}</p>
        <p class="subtitle">{listing.location}</p>
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

    p {
        line-height: 24px;
    }

    .title {
        font-size: 18px;
        font-weight: 500;
    }

    .subtitle {
        font-size: 15px;
    }
</style>
