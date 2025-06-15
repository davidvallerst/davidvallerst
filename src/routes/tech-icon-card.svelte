<script lang="ts">
	const { iconUrl, iconColor = '#33ef44' } = $props();
	function changeGradientColorVariable() {
		document.documentElement.style.setProperty('--ending-gradient-color', iconColor.toString());
	}
</script>

<button id="container" onclick={changeGradientColorVariable}>
	<img src={iconUrl} alt="icono de tecnologia" width="100%" height="100%" />
</button>

<style>
	#container {
		/* background-color: #eee8ec2f; */
		border-radius: 2rem;
		height: auto;
		padding: 1rem;
		position: relative;
		transition: transform, background-color, 100ms;
		background-color: var(--color-blue-50);
	}
	#container:hover {
		transform: scale(1.1);
		z-index: 1000;
	}

	img {
		margin: auto;
		object-fit: cover;
	}
</style>
