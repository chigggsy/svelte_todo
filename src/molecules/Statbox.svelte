<script>
    import Label from "../atoms/Label.svelte";
    export let labelMessage;
    export let isComplete = false;
</script>

<div class="statbox_wrapper">
    <div class="row">
        <Label {labelMessage} />
        <Label labelMessage="Tasks" isDim />
    </div>
    {#if isComplete}
        <Label labelMessage="Completed" isDim />
    {:else}
        <Label labelMessage="Abandoned" isDim />
    {/if}
</div>

<style>
    .statbox_wrapper {
        display: flex;
        flex-direction: column;
        align-items: end;
        justify-content: end;
        gap: 0.1rem;
    }
    .row {
        display: flex;
        justify-content: end;
        gap: 0.2rem;
    }
</style>
