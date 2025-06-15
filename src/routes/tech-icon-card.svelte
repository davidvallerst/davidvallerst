<script lang="ts">
	const { iconUrl } = $props();
</script>

<div id="container">
	<img src={iconUrl} alt="icono de tecnologia" width="100%" height="100%" />
</div>

<style>
	#container {
		/* background-color: #eee8ec2f; */
		border-radius: 2rem;
		height: auto;
		padding: 1rem;
		position: relative;
		transition: transform, background-color, 100ms;
		background-color: #efefef;
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
