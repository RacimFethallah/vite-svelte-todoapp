<script lang="ts">
	import TodoForm from '../components/TodoForm.svelte';
	import TodoList from '../components/TodoList.svelte';

	let todos: Todo[] = [];

	function addTodo(title: string) {
		if (title) {
			todos = [...todos, { id: Date.now(), title, completed: false }];
		}
	}

	function removeTodo(id: number) {
		todos = todos.filter((todo) => todo.id !== id);
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
