<script lang="ts">
    import logo from "../assets/logo_small.jpg";
    import icon from "../assets/icon.png";
    import { currentPage } from "../store";
</script>

<div class="outer">
    <div class="titlebar">
        <div class="inner">
            <img alt="Logo" src={logo} /><button
                on:click={() => currentPage.set("home")}>Dashboard</button
            ><button on:click={() => currentPage.set("jobs")}
                >Job Listings</button
            ><button on:click={() => currentPage.set("cv")}>CV Builder</button
            ><button class="right"
                >John Doe<img
                    src={icon}
                    class="profile-pic"
                    alt="John Doe"
                /></button
            >
        </div>
    </div>

    <div class="content-wrapper">
        <div class="content inner">
            <slot />
        </div>
    </div>
</div>

<style>
    .outer {
        width: 100vw;
        height: 100vh;
    }

    .inner {
        max-width: 1100px;
        margin: 0 auto;
    }

    .titlebar {
        background-color: hsl(202, 60%, 40%);
        height: 50px;
    }

    .titlebar img {
        height: 50px;
        vertical-align: middle;
    }

    .titlebar button {
        color: #fff;
        height: 50px;
        display: inline-block;
        vertical-align: middle;
        transition: background-color 0.2s ease;
        padding: 0 16px;
        font-size: 14px;
        cursor: pointer;
    }

    .titlebar button:hover {
        background-color: hsl(202, 60%, 50%);
    }

    .titlebar button.right {
        float: right;
        padding-right: 0;
    }

    .profile-pic {
        margin-left: 16px;
    }

    .content-wrapper {
        max-height: calc(100vh - 50px);
    }

    .content {
        padding: 16px 32px;
    }
</style>
