<script lang="ts">
    let icon;

    export { icon };
</script>

<div>
    <img src={icon} />
    <span>
        <p class="title">Aerospace Engineer - Remote</p>
        <p class="org">RocketLab</p>
    </span>
</div>

<style>
    div {
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
</style>
