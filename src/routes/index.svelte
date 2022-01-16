<script>

    let todos = [
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

    const markAsComplete = (index) => {
        console.log(index)
    }

</script>

<input type="text" bind:value={task}>
<button on:click={addTodo}>Add</button>

<ol>
    {#each todos as todo, index }
        <li class:completed={todo.isComplete}>
            <span>{todo.task}</span>
            <span>
                <button on:click={() => markAsComplete(index)}>✓</button>
            </span>    
        </li>
    {/each}
</ol>

<style>
    .completed {
        text-decoration: line-through;
    }
</style>