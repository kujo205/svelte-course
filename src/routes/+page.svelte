<script>
	let user = {
		loggedIn: false
	};

	function toggle() {
		user.loggedIn = !user.loggedIn;
	}
</script>

{#if user.loggedIn}
	<p>
		User is logged in, log em out
	</p>
	<button class="btn primary" on:click={toggle}>
		Log out
	</button>
{/if}


{#if !user.loggedIn}
	<p>
		User is not logged in, log em in
	</p>
	<button class="btn secondary" on:click={toggle}>
		Log in
	</button>
{/if}


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
