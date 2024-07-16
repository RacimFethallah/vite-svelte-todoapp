<script lang="ts">
	export let todos: Todo[];


	
</script>

<div>
	{#each todos as todo}
		<div>
			<span>{todo.title}</span>
			<input class="float-right" type="checkbox" bind:checked={todo.completed} />
		</div>
	{/each}
</div>
