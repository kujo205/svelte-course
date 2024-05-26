<script lang="ts">

	let count = 0;

	$: itemsTitle = count === 1 ? 'item' : 'items';
	$: console.log('Count changed:', count);
</script>


<div class="wrapper">
	<div>
		<button class="btn primary" on:click={()=>{count=count + 1}}>Increment</button>
		<button class="btn secondary" on:click={()=>{count=count - 1}}>Decrement</button>
	</div>
	<div>Count: {count} {itemsTitle}</div>
</div>


<style>
    :root {
        --primary: #007bff;
        --secondary: white;
    }

    .wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 3rem;
    }

    .btn {
        border: 1px solid transparent;
        padding: 10px 20px;
        border-radius: 5px;
        cursor: pointer;

        &.primary {
            background-color: var(--primary);
            color: var(--secondary);

            &:hover {
                background-color: var(--primary);
            }

            &:active {
                background-color: #035dc5;
            }
        }

        &.secondary {
            background-color: white;
            color: #007bff;

            &:hover {
                background-color: #f1f1f1;
            }

            &:active {
                background-color: var(--primary);
                color: var(--secondary);
            }
        }

    }
</style>
