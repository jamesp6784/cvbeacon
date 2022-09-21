<script lang="ts">
    import BasePage from "./BasePage.svelte";
    import JobWidget from "./widgets/JobWidget.svelte";
</script>

<BasePage>
    <h1>Welcome, <strong>John Doe</strong></h1>
    <JobWidget />
</BasePage>

<style>
    h1 {
        font-weight: 400;
        margin-bottom: 32px;
    }
</style>
