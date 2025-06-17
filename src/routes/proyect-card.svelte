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
		margin: 1.2rem;
		margin-top: 1rem;
		gap: 1rem;
		width: 32rem;
		background: #fff;
		border-radius: 0.5rem;

		.h-main {
			/* background: var(--color-slate-900); */
			/* background: #0007; */
			background: #fff;
			color: #223;
			margin-inline: auto;
			font-size: large;
			padding: 0.8rem;
			border-radius: 0.4rem;
		}

		.details-button {
			cursor: pointer;
			border-radius: 0.4rem;
			padding: 16px;
			background: linear-gradient(to right, #fff, #271f56);
			display: flex;
			align-items: center;
			justify-content: end;
			i {
				font-size: large;
			}
		}
	}
</style>
