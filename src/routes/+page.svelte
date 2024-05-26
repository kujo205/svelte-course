<script>
	let todos = [
		{ id: 1, text: 'Todo 1', completed: true },
		{ id: 2, text: 'Todo 2', completed: false },
		{ id: 3, text: 'Todo 3', completed: false },
		{ id: 4, text: 'Todo 4', completed: false }
	];
</script>

<ul>
	{#each todos as { text, completed }}
		<li>
			<input checked={completed} type="checkbox" />
			<span>{text}</span>
		</li>
	{/each}
</ul>

