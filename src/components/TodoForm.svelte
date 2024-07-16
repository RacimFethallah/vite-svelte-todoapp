<script lang="ts">
	let todo = '';

	export let handleAddTodo: (newTodo: string) => void;

	function addTodo() {
		if (todo.trim()) {
			handleAddTodo(todo);
			todo = ''; // Reset the input field
		}
	}
</script>

<div class="my-4">
	<input
		bind:value={todo}
		type="text"
		placeholder="Add a new todo"
		class="p-2 border rounded mr-2"
	/>
	<button class="bg-blue-500 text-white p-2 rounded" on:click={addTodo}> Add Todo </button>
</div>
