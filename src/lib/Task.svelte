
<script lang="ts">
    export let content: string;
    export let completed: boolean;
</script>

<section class="task-content">
    <span class="black-left-border"></span>
    <input type="checkbox" bind:checked="{completed}" class="task-checkbox w-5 h-5"/>
    <input type="text" bind:value="{content}" 
    disabled={completed}
    class="disabled:opacity-50 disabled:line-through"/> 
</section>

<style>

.task-content {
    position: relative;
    width: 100%;
    height: 6vh;
    background-color: rgb(255, 255, 255);
    display: flex;
    justify-content: start;
    align-items: center;
    margin-top: 1%;
    border-radius: 3px;
}

.black-left-border {
    position: absolute;
    left: 0%;
    height: 100%;
    width: 1.5%;
    background-color: rgb(40, 40, 40);
    border-top-left-radius: 3px;
    border-bottom-left-radius: 3px;
}

.task-checkbox {
    margin-right: 7px;
    margin-left: calc(1.5% + 20px);
    border-radius: 10px;
    border: 0;
    outline-style: none;
}

</style>