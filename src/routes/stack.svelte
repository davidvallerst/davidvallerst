<script lang="ts">
	import { onDestroy } from 'svelte';
	import CarouselItem from './carousel-item.svelte';

	let currentIndex = 0;

	const slides = [
		{
			title: 'Bienvenido al Carrusel',
			description: 'Este es un ejemplo de una tarjeta con imagen, título y descripción.',
			imageUrl: './icons/angular.svg'
		},
		{
			title: 'Explora más',
			description: 'Puedes agregar cualquier tipo de contenido dentro del carrusel.',
			imageUrl: './icons/golang.svg'
		},
		{
			title: 'Diseño moderno',
			description: 'Este carrusel se adapta fácilmente a cualquier diseño responsive.',
			imageUrl: './icons/docker.svg'
		}
	];
	function next() {
		currentIndex = (currentIndex + 1) % slides.length;
		autoplayInterval.refresh();
	}

	function prev() {
		currentIndex = (currentIndex - 1 + slides.length) % slides.length;
		autoplayInterval.refresh();
	}
	let autoplay = true;
	let intervalDuration = 3000; // 3 segundos

	let autoplayInterval = setInterval(() => {
		setTimeout(() => {
			if (autoplay) {
				next();
			}
		}, intervalDuration);
	}, intervalDuration);

	// Limpia el intervalo cuando el componente se destruye
	onDestroy(() => {
		clearInterval(autoplayInterval);
	});
</script>

<!-- Carrusel -->
<div class="carousel-container">
	{#each slides as slide, index}
		<CarouselItem
			title={slide.title}
			description={slide.description}
			imageUrl={slide.imageUrl}
			active={index === currentIndex}
		/>
	{/each}

	<div class="controls" style:display="none">
		<button onclick={prev}><i class="pi pi-angle-left"></i> Anterior</button>
		<button onclick={next}>Siguiente <i class="pi pi-angle-right"></i></button>
	</div>
</div>

<style>
	.carousel-container {
		background-color: var(--light-bg-color);
		width: 79vw;
		height: 500px;
		padding: 40px;
		border-radius: 12px;
		box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
		position: relative;
		overflow: hidden;
		font-family: 'Segoe UI', sans-serif;
		color: #333;
		margin: 50px auto;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		text-align: center;
	}

	.controls {
		position: absolute;
		bottom: 14px;
		display: flex;
		width: 100%;
		justify-content: space-between;
		padding-inline: 1rem;
	}

	button {
		padding: 10px 18px;
		font-size: 1rem;
		background-color: var(--starting-gradient-color);
		color: white;
		border: none;
		border-radius: 6px;
		cursor: pointer;
		transition: background-color 0.2s ease;
		z-index: 100;
	}

	button:hover {
		background-color: var(--ending-gradient-color);
	}
</style>
