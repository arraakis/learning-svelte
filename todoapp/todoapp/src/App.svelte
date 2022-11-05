<script>
  import TodoForm from "./TodoForm.svelte";

  let todos = [];

  function addTodo(todo) {
    todos.push({
      title: todo,
      done: false,
    });

    console.log(todos);

    todos = todos;
  }

  function removeTodo(index) {
    todos.splice(index, 1);
    todos = todos;
  }
</script>

<main>
  <TodoForm {addTodo} />

  <ul>
    {#each todos as todo, index}
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <li class="todo" class:done={todo.done}>
        {#if todo.done}
          <span>✅</span>
        {/if}

        <span on:click={() => (todo.done = !todo.done)}>
          {todo.title}
        </span>
        <span class="delete" on:click={() => removeTodo(index)}> 🗑️ </span>
      </li>
    {/each}
  </ul>
</main>

<style>
  .todo {
    cursor: pointer;
  }
  .done {
    text-decoration: line-through;
  }

  .delete {
    display: inline-block;
  }
  .delete:hover {
    transform: scale(2);
  }
</style>
