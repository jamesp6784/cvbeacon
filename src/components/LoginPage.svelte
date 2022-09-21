<script lang="ts">
    import { currentPage } from "../store";
    import logo from "../assets/logo.png";

    function login() {
        currentPage.set("home");
    }
</script>

<div class="outer">
    <div class="inner">
        <img alt="Logo" src={logo} />
        <h1>Login to AUT</h1>
        <input placeholder="Username / Email" />
        <input type="password" placeholder="Password" />
        <a href="https://my.aut.ac.nz/">Forgot password?</a>
        <button on:click={login}>Login</button>
    </div>
</div>

<style>
    .outer {
        width: 100vw;
        height: 100vh;
    }

    .inner {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        display: inline-block;
        padding: 32px 32px;
        background-color: #fff;
        box-shadow: 0 0 5px #00000033;
    }

    img {
        width: 260px;
        margin-bottom: 16px;
    }

    h1 {
        font-size: 24px;
        margin-bottom: 24px;
    }

    a {
        font-size: 14px;
    }

    input {
        display: block;
        padding: 12px;
        font-size: 14px;
        background-color: #eee;
        margin-bottom: 8px;
        width: 100%;
        border-bottom: 2px solid hsla(202, 60%, 40%, 0);
        transition: border-bottom 0.1s ease;
    }

    input:focus {
        border-bottom: 2px solid hsl(202, 60%, 40%);
    }

    button {
        display: block;
        background-color: hsl(202, 60%, 40%);
        padding: 8px;
        margin-top: 32px;
        width: 100%;
        font-weight: 600;
        color: #fff;
        transition: background-color 0.2s ease;
        cursor: pointer;
    }

    button:hover {
        background-color: hsl(202, 60%, 50%);
    }
</style>
