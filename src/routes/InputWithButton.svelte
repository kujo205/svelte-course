<script lang="ts">
	import { title } from '../stores/example';
	import Button from '../components/Button.svelte';

	let value = '';

	function updateTitle() {
		$title = value;
		value = '';
	}

</script>

<div class="wrapper">
	<h2>
		Enter some value
	</h2>
	<div class="row">
		<input class="input" bind:value={value} />
		<Button on:click={updateTitle} class="one-line">
			Update store
		</Button>
	</div>
</div>


<style>
    .one-line {
        white-space: nowrap;
    }

    .row {
        display: flex;
        gap: 16px;
    }

    .wrapper {
        display: flex;
        flex-direction: column;
    }

    .input {
        width: 100%;
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
        margin-bottom: 10px;
    }
</style>
