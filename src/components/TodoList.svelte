<script lang="ts">

export let todos: Todo[];


</script>

<div>
	{#each todos as todo, i}
		<div>
			<span>{todo.title}</span>
			<input class="float-right" type="checkbox" bind:checked={todo.completed} />
			<!-- <button onclick={() => removeTodo(todo.id)}>remove</button> -->
		</div>
	{/each}
</div>
