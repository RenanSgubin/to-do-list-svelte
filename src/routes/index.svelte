
<script lang="ts">
    import { text } from "svelte/internal";
    import Task from "../lib/Task.svelte";

    interface iTask {
        text: string;
        completed: boolean;
    }

    let tasks: iTask[] = [
        {
            text: "Minha tarefa",
            completed: true
        },
        {
            text: "Minha tarefa",
            completed: false
        }
    ];

    function addTask() {
        tasks = [...tasks, {
            text: "Minha task criada por função",
            completed: false
        }];
    }

</script>

<section class="app-container">
    <div class="app-content">
        {#each tasks as task}
            <Task bind:content={task.text} bind:completed={task.completed}/>
        {/each}
        <button class="add-task" on:click="{addTask}">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 9v3m0 0v3m0-3h3m-3 0H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z" />
            </svg>
            <span>Add Task</span>
        </button>
    </div>
</section>


<style>
    .app-container {
        width: 100%;
        height: 100vh;
        background-color: rgb(147, 195, 237);
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .app-content {
        width: 450px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .add-task {
        width: 100%;
        height: 7vh;
        background-color: rgb(124, 185, 238);
        display: flex;
        justify-content: center;
        align-items: center;
        border: 2px black dashed;
        margin-top: 2%;
        border-radius: 5px;
        color: rgb(232, 232, 232);
    }

    .add-task:hover {
        color: rgb(246, 246, 246);
    }

    .add-task span {
        margin-left: 7px;
    }
</style>