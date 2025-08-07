<script>
	let todos = $state([{ text: 'Fly to the moon', done: false }]),
		done = $derived(todos.filter((t) => t.done).length),
		onchange = (e) => todos.push({ text: e.target.value, done: false }) && (e.target.value = '');
</script>

<input {onchange} />
{#each todos as todo}
	<div>
		<input bind:value={todo.text} />
		<input type="checkbox" bind:checked={todo.done} />
	</div>
{/each}
Done: {done}
