<script lang="ts">
	type Track = {
		title: string;
		length: string;
	};
	import AlbumTrack from './AlbumTrack.svelte';

	export let albumTitle: string;
	export let albumTracks: Track[] = [];
	let playing: string;

	function setPlaying(track: string) {
		playing = track;
	}
</script>

<h2>{albumTitle}</h2>

<ul>
	{#each albumTracks as track}
		<AlbumTrack {setPlaying} {playing} {...track} />
	{/each}
</ul>
