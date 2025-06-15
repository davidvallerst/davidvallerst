<script lang="ts">
</script>

<div class="highlight-container">
	<div class="h-main" style:padding="2rem">
		<h2>Proyecto 3</h2>
		Lorem ipsum dolor sit amet consectetur... Lorem ipsum dolor sit, amet consectetur adipisicing elit.
	</div>

	<div class="details-button">
		<div class="more">Ver más</div>
		<i class="pi pi-angle-right"></i>
	</div>
</div>

<style>
	.highlight-container {
		display: flex;
		flex-direction: column;
		padding: 1.2rem;
		margin-top: 1rem;
		gap: 1rem;
		width: 32rem;

		.h-main {
			/* background: var(--color-slate-900); */
			background: #00000022;
			backdrop-filter: blur(10px);

			margin-inline: auto;
			font-size: large;
			padding: 0.8rem;
			border-radius: 0.4rem;
		}

		.details-button {
			cursor: pointer;
			border-radius: 0.4rem;
			padding: 16px;
			background: var(--color-slate-900);
			display: flex;
			align-items: center;
			justify-content: end;
			i {
				font-size: large;
			}
		}
	}
</style>
