<script lang="ts">
	let mousePosition = {
		x: 0,
		y: 0
	};

	const handleMousePositionChange = (event: MouseEvent) => {
		mousePosition = {
			x: event.clientX,
			y: event.clientY
		};
	};


</script>


<div class="wrapper" on:mousemove|stopPropagation={handleMousePositionChange}>
	<p> x: {mousePosition.x} </p>
	<p> y: {mousePosition.y} </p>
</div>

<style>
    :root {
        --primary: #007bff;
        --secondary: white;
    }

    .wrapper {
        width: 90vw;
        height: 90vh;
    }

</style>
