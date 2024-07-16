<script lang="ts">
	let todo = $state('');

	let { handleAddTodo } = $props<{}>();
</script>

<div class="my-4">
	<input
		onkeydown={(e) => {
			if (e.key === 'Enter') {
				handleAddTodo(todo);
				todo = '';
			}
		}}
		bind:value={todo}
		type="text"
		placeholder="Add a new todo"
		class="p-2 border rounded mr-2"
	/>
	<button
		class="bg-blue-500 text-white p-2 rounded"
		onclick={() => {
			handleAddTodo(todo);
			todo = '';
		}}
	>
		Add Todo
	</button>
</div>
