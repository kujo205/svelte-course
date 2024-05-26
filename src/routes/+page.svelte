<script lang="ts">
	let list = ['React', 'Vue', 'Svelte'];
	let filteredList: string[] = [];
	let searchQuery = '';

	function filterList() {
		filteredList = list.filter(item => {
			return item
				.toLowerCase()
				.includes(searchQuery.toLowerCase());
		});
	}
</script>

<input
	on:input={filterList}
	bind:value={searchQuery}
	type="text"
/>

<ul>
	{#each filteredList as item}
		<li>{item}</li>
	{/each}
</ul>


<style>
    :root {
        --primary: #007bff;
        --secondary: white;
    }


</style>
