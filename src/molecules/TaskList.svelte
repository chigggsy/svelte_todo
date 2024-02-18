<script>
    import Label from "../atoms/Label.svelte";
    import Task from "./Task.svelte";

    const taskList = [
        { taskMessage: "Convert to components", id: 1 },
        { taskMessage: "Create a new svelte app", id: 2 },
        { taskMessage: "Build svelte components", id: 3 },
        { taskMessage: "Start the Advent Of Svelte", id: 4 },
    ];
</script>

<div class="tasklist">
    <Label labelMessage="Tasks at hand" />
    <div class="tasks_wrapper">
        {#each taskList as task (task.id)}
            <Task taskMessage={task.taskMessage} />
        {/each}
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
