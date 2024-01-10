<script>
  import Todo from "./Todo.svelte";
  import { writable } from "svelte/store";

  let title = "";
  let todos = writable([]);
  let id = 0;

  function createTodo() {
    $todos.push({
      id,
      title,
    });
    // 할당을 통해서 반응성을 유지
    $todos = $todos;
    title = "";
    id += 1;
  }
</script>

<input
  bind:value={title}
  type="text"
  on:keydown={(e) => {
    e.key === "Enter" && createTodo();
  }}
/>
<button on:click={createTodo}> Create Todo </button>

{#each $todos as todo}
  <Todo {todos} {todo} />
{/each}
