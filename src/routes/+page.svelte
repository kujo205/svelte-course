<script lang="ts">
	let pokemons = [
		'charizard',
		'pikachu',
		'bulbasaur',
		'charmander',
		'squirtle'
	];

	let pokemonIndex = 0;


	function updatePokemonIndex(index: number) {
		if (index < 0) {
			pokemonIndex = pokemons.length - 1;
		} else {

			if (index >= pokemons.length) {
				pokemonIndex = 0;
			} else {
				pokemonIndex = index;
			}
		}
	}

	async function fetchPokemon(pokemonName: string) {
		let url = `https://pokeapi.co/api/v2/pokemon/`;
		let response = await fetch(`${url}${pokemonName}`);
		let { name, sprites } = await response.json();

		return {
			name,
			image: sprites['front_default']
		};
	}
</script>

<div class="wrapper">
	{#await fetchPokemon(pokemons[pokemonIndex])}
		<p>
			Fetching a pokemon
		</p>
	{:then pokemon}
		<h1>Pokemon : {pokemon.name}</h1>
		<img src={pokemon.image} alt={pokemon.name} />
	{:catch error}
		<p>
			Something went wrong: {error.message}
		</p>
	{/await}
</div>

<div class="btn-wrapper">
	<button on:click={()=>updatePokemonIndex(pokemonIndex - 1)}>
		Previous pokemon
	</button>

	<button on:click={()=>updatePokemonIndex(pokemonIndex + 1)}>
		Next pokemon
	</button>
</div>

<style>
    .wrapper {
        display: flex;
        flex-direction: column;
    }

    .btn-wrapper {
        display: flex;
        gap: 3rem;
    }
</style>
