<script lang="ts">
	export let setPlaying: (title: string) => void;
	export let playing: string;
	export let title: string;
	export let length: string;


</script>

<li class:playing={playing===title}>
	<button on:click={() => setPlaying(title)}>▶️</button>
	<span>{title}</span>
	<span>🕒️ {length}</span>
</li>

<style>
    .playing {
        color: teal;
    }
</style>
