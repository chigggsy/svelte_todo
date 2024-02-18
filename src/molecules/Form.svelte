<script>
    import Label from "../atoms/Label.svelte";
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    let taskMessage;

    const handleSubmit = () => {
        const task = {
            taskMessage,
            id: Math.random(),
        };
        dispatch("addTask", task);
    };
</script>

<div>
    <Label labelMessage="Add A Task" />
    <form on:submit|preventDefault={handleSubmit}>
        <input class="type-main" type="text" placeholder="e.g. Learn Svelte" />
        <input class="type-main" type="submit" value="Add" />
    </form>
</div>

<style>
    div {
        display: flex;
        flex-direction: column;
        gap: 2.5rem;
    }

    form {
        display: flex;
        width: 100%;
    }

    input[type="text"] {
        width: 100%;
        margin: 0;
        padding: 0;
        border: none;
        background: none;
    }
    input[type="text"]:focus {
        outline: none;
    }
    input[type="text"]::placeholder {
        color: var(--color-dim);
        opacity: 1;
    }

    input[type="submit"] {
        margin: 0;
        padding: 0;
        border: none;
        font-size: var(--type-main-size);
        font-weight: 300;
        line-height: 100%;
        letter-spacing: -0.02em;
        color: var(--color-white);
        background: none;
        cursor: pointer;
    }
</style>
