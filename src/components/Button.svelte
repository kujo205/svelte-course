<script lang="ts">
	import type { HTMLButtonAttributes } from 'svelte/elements';

	interface $$Props extends HTMLButtonAttributes {
		variant?: TVariant;
	}

	const { class: className } = $$restProps;

	type TVariant = 'primary' | 'secondary';
	export let variant: TVariant = 'primary';
</script>


<button {...$$restProps} class={'btn ' + variant + ' ' + className} on:click>
	<slot />
</button>


<style>
    .btn {
        border-radius: 8px;
        padding: .5rem 1rem;

        &:hover, &:active {
            cursor: pointer;
        }
    }

    .primary {
        background-color: #5874dc;
        color: white;


        &:hover, &:active {
            background-color: #3f5fcd;
        }
    }

    .secondary {
        background-color: #ea937a;
        color: white;

        &:hover, &:active {
            background-color: #f67b51;
        }
    }

</style>
