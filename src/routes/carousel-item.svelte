<script>
	export let active = false;
	export let title = 'Título predeterminado';
	export let description = 'Descripción corta...';
	export let imageUrl = 'https://via.placeholder.com/600x300?text=Imagen+Predeterminada';
</script>

<div class="card-slide" class:active>
	<img src={imageUrl} alt={title} />
	<h3>{title}</h3>
	<p>{description}</p>
</div>

<style>
	.card-slide {
		text-align: center;
		padding: 1rem;
		box-sizing: border-box;
	}

	.card-slide img {
		width: 100%;
		max-width: 100%;
		height: auto;
		border-radius: 8px;
		margin-bottom: 1rem;
	}

	.card-slide h3 {
		font-size: 1.2rem;
		color: #333;
		margin-bottom: 0.5rem;
	}

	.card-slide p {
		font-size: 1rem;
		color: #666;
		line-height: 1.4;
	}

	.card-slide {
		width: 100%;
		font-size: 1.5rem;
		line-height: 1.6;
		opacity: 0;
		transition: opacity 0.6s ease-in-out;
		position: absolute;
	}

	.card-slide.active {
		opacity: 1;
	}
</style>
