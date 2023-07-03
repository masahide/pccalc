<script lang="ts">
	import { onMount } from 'svelte';
	let theme: string = '';

	const setSvgFill = (element: SVGElement, color: string) => {
		element.querySelectorAll('*').forEach((el) => {
			if (el instanceof SVGElement) {
				el.setAttribute('fill', color);
			}
		});
	};
	const loadLogo = (text: string) => {
		const parser = new DOMParser();
		const svgDoc = parser.parseFromString(text, 'image/svg+xml');

		theme = document.documentElement.getAttribute('data-bs-theme') || '';

		// もしテーマが'dark'ならfillを白に設定し、'light'ならfillを黒に設定
		const fill = theme === 'dark' ? 'white' : 'black';

		if (svgDoc.documentElement instanceof SVGElement) {
			setSvgFill(svgDoc.documentElement, fill);
		}

		// SVGをDOMに追加する
		const container = document.querySelector('#svg-container');
		if (container) {
			container.appendChild(svgDoc.documentElement);
		}
	};

	onMount(async () => {
		const response = await fetch('./svg/pccalc_icon.svg');
		loadLogo(await response.text());
	});
</script>

<!-- <img class="d-block mx-auto mb-4" src="./svg/pccalc_icon.svg" alt="" width="72" height="57">-->
<div id="svg-container" class="d-block mx-auto mb-4" />

<style>
	:global(#Layer_1) {
		fill: white;
	}

	#svg-container {
		width: 72px;
		height: 57px;
	}
</style>
