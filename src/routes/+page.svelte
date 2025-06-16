<script lang="ts">
	import ProyectCard from './proyect-card.svelte';
	import TechIconCard from './tech-icon-card.svelte';

	let r = 0;
	let g = 0;
	let b = 0;
	let objR = 255;
	let objG = 255;
	let objB = 255;
	// $effect(() => {
	// 	function getRGB(key: string) {
	// 		return getComputedStyle(document.documentElement).getPropertyValue(key).replaceAll('#', '');
	// 	}
	// 	const [rn, gn, bn] = getRGB('--ending-gradient-color');
	// 	const [rl, gl, bl] = getRGB('--last-gradient-color');
	// 	r = parseInt(rn);
	// 	g = parseInt(gn);
	// 	b = parseInt(bn);
	// 	objR = parseInt(rl);
	// 	objG = parseInt(gl);
	// 	objB = parseInt(bl);
	// });
	// function onScrollChangeColor() {
	// 	const maxScroll = document.documentElement.scrollHeight - window.innerHeight;

	// 	const scrollRatio = window.scrollY / maxScroll;
	// 	const rn = Math.round(r + (objR - r) * scrollRatio);
	// 	const gn = Math.round(g + (objG - g) * scrollRatio);
	// 	const bn = Math.round(b + (objB - b) * scrollRatio);
	// 	document.body.style.setProperty('--ending-gradient-color', `rgb(${rn},${gn},${bn})`);
	// }
</script>

<!-- <svelte:window on:scroll={onScrollChangeColor} /> -->
<section id="hero">
	<header
		style:display="flex"
		style:align-items="center"
		style:backdrop-filter="blur(100px)"
		style:background="#0007"
		style:gap="10px"
		style:padding="20px"
	>
		<div
			style:height="50px"
			style:width="50px"
			style:background="white"
			style:color="#222"
			style:border-radius="50%"
		>
			V3
		</div>
		<div style:display="flex" style:flex-direction="column">
			<a href="./" style:font-size="1.2rem" style:color="#def">Correo → davidvalle.rst@gmail.com</a>
			<a href="./" style:font-size="1.2rem" style:color="#def">Correo → davidvallerst</a>
		</div>
	</header>
	<h1
		id="presentation-title"
		style:text-align="center"
		style:margin-inline="auto"
		style:padding-inline="1rem"
		style:margin-top="2rem"
	>
		Elvis David Hernandez
		<br />
		Desarrollador Web full stack
	</h1>
	<div
		id="icons"
		style:display="grid"
		style:gap="1rem"
		style:max-width="max(60rem, 50vw)"
		style:margin="auto"
		style:justify-content="center"
		style:align-items="center"
		style:margin-top="3rem"
		style:padding-inline="1rem"
	>
		<TechIconCard iconUrl="./icons/angular.svg" />
		<TechIconCard iconUrl="./icons/nestjs.svg" />
		<TechIconCard iconUrl="./icons/java.svg" />
		<TechIconCard iconUrl="./icons/spring.svg" />
		<TechIconCard iconUrl="./icons/sql.svg" />
		<TechIconCard iconUrl="./icons/golang.svg" />
		<TechIconCard iconUrl="./icons/http.svg" />
		<TechIconCard iconUrl="./icons/docker.svg" />
		<TechIconCard iconUrl="./icons/git.svg" />
	</div>
</section>
<section style:background="#eee" style:color="#333" style:padding="2rem 0rem 4rem 0rem">
	<div class="hr"></div>
	<h2 style:margin-inline="auto" style:padding-inline="1rem" style:text-align="center">
		Bienvenid@ a mi Portafolio
	</h2>
	<div style:margin-top="4rem" style:padding-inline="6rem">
		<p>Mi nombre es Elvis David Hernandez Valle</p>
		<p>
			Soy desarrollador web full stack con experiencia en distintos proyectos que me han ayudado a
			forjar habilidades en el desarrollo de software
		</p>
	</div>
</section>
<section style:margin-top="3rem">
	<div class="hr"></div>
	<h2
		style:margin-left="4rem"
		style:margin-block="3rem"
		style:margin-inline="auto"
		style:margin-bottom="3rem"
		style:padding-inline="1rem"
		style:text-align="center"
	>
		Proyectos Destacados
	</h2>
	<div class="highlights">
		<ProyectCard />
		<ProyectCard />
		<ProyectCard />
	</div>
</section>
<div class="cv-section p-16">
	<p>Para mas informacion</p>
	<h3>
		Descargar CV ->
		<a class="text-slate-300" style:font-size="2rem" style:font-weight="bold" href="./"
			>curriculum vitae Elvis D Hernandez Valle</a
		>
	</h3>
</div>
<footer style:height="100px"></footer>

<style>
	#hero {
		min-height: 100vh;
	}
	#presentation-title::before {
		content: '< ';
	}
	#presentation-title::after {
		content: ' />';
	}
	#icons {
		grid-template-columns: repeat(auto-fill, minmax(7rem, 1fr));
	}
	@media (min-width: 900px) {
		#icons {
			grid-template-columns: repeat(auto-fill, minmax(10rem, 1fr));
		}
	}
	p {
		font-size: 1.4rem;
		font-weight: 600;
	}
	.highlights {
		display: flex;
		flex-wrap: wrap;
		margin: auto;
		justify-content: center;
	}
</style>
