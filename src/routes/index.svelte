<script>

    let todos = [
        {task: "Get bread", isComplete:true, createdAt: "2022-01-15"},
        {task: "Get milk", isComplete:false, createdAt: "2022-01-15"},
        {task: "Get eggs", isComplete:false, createdAt: "2022-01-15"}
    ]

    let task = "";
    
    const addTodo = () => {
        let todo = {
            task: task,
            isComplete: false,
            createdAt: new Date()
        }
        todos = [...todos, todo]
        task = ""
    }

</script>

<input type="text" bind:value={task}>
<button on:click={addTodo}>Add</button>

<ol>
    {#each todos as todo }
        <li class:completed={todo.isComplete}>{todo.task}</li>
    {/each}
</ol>

<style>
    .completed {
        text-decoration: line-through;
    }
</style>