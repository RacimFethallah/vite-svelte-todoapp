<script lang="ts">
	import TodoForm from '../components/TodoForm.svelte';
	import TodoList from '../components/TodoList.svelte';

	let todos: Todo[] = $state([]);

	function addTodo(title: string) {
		if (title) {
			todos.push({
				id: todos.length + 1,
				title,
				completed: false
			});
		}
	}
</script>

<svelte:head>
	<title>ToDo app</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<div class=" max-w-xl mx-auto my-8 p-8 bg-white rounded-lg shadow">
	<h1 class="text-3xl font-bold mb-4 text-center">Svelte Todo App</h1>

	<TodoForm handleAddTodo={addTodo} />
	<TodoList {todos} />
</div>
