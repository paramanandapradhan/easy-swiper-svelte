<script lang="ts">
	import EasyScriptLoader from '@cloudparker/easy-script-loader-svelte';
	export let script: string = 'https://cdn.jsdelivr.net/npm/swiper@9/swiper-bundle.min.js';
	export let style: string = 'https://cdn.jsdelivr.net/npm/swiper@9/swiper-bundle.min.css';
</script>

<EasyScriptLoader scriptName="Swiper" {script} {style} on:load>
	<slot />
</EasyScriptLoader>
