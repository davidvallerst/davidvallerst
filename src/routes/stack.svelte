<script lang="ts">
	let currentIndex = 0;
	const texts = [
		'La vida es lo que pasa mientras estás ocupado haciendo otros planes.',
		'No intentes ser una persona de éxito. Sé una persona de valor.',
		'La única forma de hacer un gran trabajo es amar lo que haces.',
		'La felicidad no es algo hecho. Viene de tus propias acciones.',
		'Piensa en grande y no mires nunca hacia atrás.'
	];

	function next() {
		currentIndex = (currentIndex + 1) % texts.length;
	}

	function prev() {
		currentIndex = (currentIndex - 1 + texts.length) % texts.length;
	}
</script>

<div class="carousel-container">
	{#each texts as text, index}
		<div class="text-slide" class:active={index === currentIndex}>
			{text}
		</div>
	{/each}

	<div class="controls">
		<button onclick={prev}>⬅ Anterior</button>
		<button onclick={next}>Siguiente ➡</button>
	</div>

	<div class="indicators">
		{#each texts as _, i}
			<button
				class="indicator"
				class:active={i === currentIndex}
				onclick={() => (currentIndex = i)}
				aria-label="Ir a slide {i + 1}"
			></button>
		{/each}
	</div>
</div>

<style>
	.carousel-container {
		background-color: #fff;
		width: 79vw;
		min-height: 550px;
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

	.text-slide {
		width: 100%;
		font-size: 1.5rem;
		line-height: 1.6;
		opacity: 0;
		transition: opacity 0.6s ease-in-out;
		position: absolute;
	}

	.text-slide.active {
		opacity: 1;
	}

	.controls {
		position: absolute;
		margin-top: 30px;
		bottom: 14px;
		display: flex;
		gap: 15px;
		justify-content: center;
	}

	button {
		padding: 10px 18px;
		font-size: 1rem;
		background-color: #0077cc;
		color: white;
		border: none;
		border-radius: 6px;
		cursor: pointer;
		transition: background-color 0.2s ease;
		z-index: 100;
	}

	button:hover {
		background-color: #005fa3;
	}

	.indicators {
		position: absolute;
		top: 0;
		margin-top: 20px;
		display: flex;
		gap: 6px;
		justify-content: center;
	}

	.indicator {
		width: 10px;
		height: 10px;
		border-radius: 2rem;
		background-color: #ccc;
		cursor: pointer;
		transition: background-color 0.3s ease;
	}

	.indicator.active {
		background-color: #0077cc;
	}
</style>
