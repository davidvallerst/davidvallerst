<script lang="ts">
</script>

<!-- Seccion de Stack -->
<!-- Para mostrar los stacks tecnologicos con los que he trabajado -->

<section>
	<div class="stack-container">
		<div class="carousel">
			<div class="item">
				Lorem ipsum dolor sit, amet consectetur adipisicing elit. Laboriosam, recusandae.
			</div>
			<div class="item">
				Sed dignissimos dolore expedita error harum quam placeat beatae repudiandae!
			</div>
			<div class="item">
				Eos aspernatur illo, autem inventore maiores minus laboriosam qui libero!
			</div>
			<div class="item">
				Error aut minima laudantium sed magni, asperiores veritatis perferendis nemo.
			</div>
			<div class="item">
				Quam iure non reiciendis cumque, quaerat doloribus in temporibus error?
			</div>
		</div>
	</div>
</section>

<style scoped>
	section {
	}
	.stack-container {
		color: #223;
		background: #fff;
		font-size: 1.2rem;
		font-weight: bold;
		min-height: 500px;
		flex-grow: 1;
		margin-inline: 10vw;
		border-radius: 20px;
		position: relative;
	}
	.item {
		width: 100%;
		height: 100%;
		padding-inline: 2rem;
		position: absolute;
	}
	.item::before {
		content: '> ';
	}
	.carousel {
		overflow: hidden;
		width: 100%;
		position: relative;
	}
	@keyframes Carousel {
		0% {
		}
		100% {
		}
	}
</style>
