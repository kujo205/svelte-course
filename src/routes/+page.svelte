<script lang="ts">

	let count = 0;

	function increment() {
		count += 1;
	}


</script>


<div class="wrapper">
	<button class="btn" on:click={increment}>Increment</button>
	<div>Count: {count}</div>
</div>


<style>
    .wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 1rem;
    }

    .btn {
        padding: 10px 20px;
        background-color: #007bff;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;

        &:hover {
            background-color: #016ce1;
        }

        &:active {
            background-color: #035dc5;
        }
    }
</style>
