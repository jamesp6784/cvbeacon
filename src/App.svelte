<script lang="ts">
    import LoginPage from "./components/LoginPage.svelte";
    import HomePage from "./components/HomePage.svelte";
    import JobsPage from "./components/JobsPage.svelte";
    import CVPage from "./components/CVPage.svelte";
    import { currentPage } from "./store";

    let state;

    currentPage.subscribe((val) => {
        state = val;
    });
</script>

<main>
    {#if state === "login"}
        <LoginPage />
    {:else if state === "home"}
        <HomePage />
    {:else if state === "jobs"}
        <JobsPage />
    {:else if state === "cv"}
        <CVPage />
    {/if}
</main>

<style>
    main {
        height: 100vh;
        width: 100vw;
        background-color: #eee;
    }
</style>
