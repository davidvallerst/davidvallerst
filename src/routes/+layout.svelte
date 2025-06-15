<script lang="ts">
	import '../app.css';
	let { children } = $props();

	//Scroll color changer
	function hexToRgb(hex: string) {
		hex = hex.replace('#', '');
		const r = parseInt(hex.substring(0, 2), 16);
		const g = parseInt(hex.substring(2, 4), 16);
		const b = parseInt(hex.substring(4, 6), 16);
		return [r, g, b];
	}
	function rgbToHex(r: number, g: number, b: number) {
		// Validar los valores de entrada
		if (r < 0 || r > 255 || g < 0 || g > 255 || b < 0 || b > 255) {
			throw new Error('Los valores RGB deben estar entre 0 y 255');
		}

		// Convertir cada componente a hexadecimal y asegurar 2 dígitos
		const toHex = (value: number) => {
			const hex = value.toString(16);
			return hex.length === 1 ? '0' + hex : hex;
		};
		// Combinar los componentes
		return `#${toHex(r)}${toHex(g)}${toHex(b)}`.toUpperCase();
	}
	function extractColor(cssKey: string) {
		return hexToRgb(getComputedStyle(document.documentElement).getPropertyValue(cssKey));
	}
	function extrapolateColors(fromColor: number[], toColor: number[], extrapolationRatio: number) {
		const r = Math.round(fromColor[0] + (toColor[0] - fromColor[0]) * extrapolationRatio);
		const g = Math.round(fromColor[1] + (toColor[1] - fromColor[2]) * extrapolationRatio);
		const b = Math.round(fromColor[2] + (toColor[2] - fromColor[2]) * extrapolationRatio);
		return rgbToHex(r, g, b);
	}
	let extrapolationRatio = 0.0;

	function logRatio() {
		extrapolationRatio =
			window.scrollY / (document.documentElement.scrollHeight - window.innerHeight);
		const finalColor = extrapolateColors(
			extractColor('--ending-gradient-color'),
			extractColor('--last-gradient-color'),
			extrapolationRatio
		);

		document.body.style.setProperty('--ending-gradient-color', finalColor);
	}
</script>

<svelte:window onscroll={logRatio} />
{@render children()}
