<script lang="ts">
    import BasePage from "./BasePage.svelte";
    import CVWidget from "./widgets/CVWidget.svelte";
</script>

<BasePage>
    <h1>CV Builder</h1>
    <CVWidget />
</BasePage>

<style>
    h1 {
        font-weight: 400;
        margin-bottom: 32px;
    }
</style>
