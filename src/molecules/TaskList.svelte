<script>
    import Label from "../atoms/Label.svelte";
    import Task from "./Task.svelte";
</script>

<div class="tasklist">
    <Label labelMessage="Tasks at hand" />
    <div class="tasks_wrapper">
        <Task task="Convert to components" />
        <Task task="Create new svelte app" />
        <Task task="Build svelte components" />
    </div>
</div>

<style>
    .tasklist {
        display: flex;
        flex-direction: column;
        gap: 2.5rem;
    }
    .tasks_wrapper {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
</style>
