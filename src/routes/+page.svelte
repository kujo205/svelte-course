<script>
	import { fade, fly, draw, blur } from 'svelte/transition';
	import Artist from './Artist.svelte';
	import Album from './Album.svelte';
	import Button from '../components/Button.svelte';

	let toggled = false;

	function toggleFade() {
		console.log('clicked');
		toggled = !toggled;
	}


	let artists = [
		{
			name: 'Fleetwood Mac',
			albums: [
				{
					name: 'Tango in the Night',
					year: 1987,
					tracks: [
						{ title: 'Big Love', length: '3:37' },
						{ title: 'Seven Wonders', length: '3:38' },
						{ title: 'Everywhere', length: '3:48' },
						{ title: 'Caroline', length: '3:50' },
						{ title: 'Tango in the Night', length: '3:56' },
						{ title: 'Mystified', length: '3:08' }
					]
				}
			]
		}
	];
</script>

{#if toggled}
	<blockquote transition:fade={{delay: 250, duration: 300}}>
		Memories fade, but friends are forever
	</blockquote>
	<blockquote transition:fly={{delay: 250, duration: 300}}>
		Memories fade, but friends are forever
	</blockquote>
	<blockquote transition:blur={{delay: 250, duration: 300}}>
		Memories fade, but friends are forever
	</blockquote>
{/if}
<Button variant={ toggled ? "primary" : "secondary"} on:click={toggleFade}>
	<span slot="icon">➕ / -</span>
	<span slot="title">Toggle fade</span>
</Button>


{#each artists as artist}
	<Artist artistName={artist.name} />
	{#each artist.albums as album}
		<Album
			albumTitle={album.name}
			albumTracks={album.tracks}
		/>
	{/each}
{/each}
