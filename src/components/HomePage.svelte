<script lang="ts">
    import BasePage from "./BasePage.svelte";
    import JobWidget from "./widgets/JobWidget.svelte";
</script>

<BasePage>
    <h1>Welcome, <strong>John Doe</strong></h1>
    <h3>Your recommended listings</h3>
    <JobWidget />
</BasePage>

<style>
    h1 {
        font-weight: 400;
        margin-bottom: 32px;
    }

    h3 {
        font-weight: 400;
        margin-bottom: 16px;
    }
</style>
