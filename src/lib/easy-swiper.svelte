<script lang="ts">
	import EasyScriptLoader from '@cloudparker/easy-script-loader-svelte';
	import { createEventDispatcher } from 'svelte';
	export let scriptUrl: string = 'https://cdn.jsdelivr.net/npm/swiper@10/swiper-bundle.min.js';
	export let styleUrl: string = 'https://cdn.jsdelivr.net/npm/swiper@10/swiper-bundle.min.css';
	export let scriptName: string = 'Swiper';
	export let swiperClass: string = '';
	export let swiperWrapperClass: string = '';
	export let swiperStyle: string = '';
	export let swiperWrapperStyle: string = '';
	export let swiperPaginationClass: string = '';
	export let swiperPaginationStyle: string = '';
	export let swiperNextBtnClass: string = '';
	export let swiperNextBtnStyle: string = '';
	export let swiperPrevBtnClass: string = '';
	export let swiperPrevBtnStyle: string = '';
	export let swiperScrollbarClass: string = '';
	export let swiperScrollbarStyle: string = '';
	export let swiperSlideClass: string = '';
	export let swiperSlideStyle: string = '';

	export let hasPagination: boolean = false;
	export let hasControlBtns: boolean = false;
	export let hasScrollbar: boolean = false;

	export let size: number = 0;

	export let swiperOptions: any = {
		slidesPerView: 3,
		spaceBetween: 8,
		freeMode: true,
		pagination: {
			clickable: true
		}
	};

	let swiperRef: HTMLDivElement;
	let dispatch = createEventDispatcher();

	function handleSwipperLoad(ev: CustomEvent) {
		let Swiper: any = ev.detail;
		const swiper = new Swiper(swiperRef, swiperOptions);
		dispatch('load', { Swiper, swiper });
	}
</script>

<EasyScriptLoader {scriptName} {scriptUrl} {styleUrl} on:load={handleSwipperLoad}>
	<div class="swiper {swiperClass}" bind:this={swiperRef} style=" {swiperStyle}">
		<div class="swiper-wrapper {swiperWrapperClass}" style=" {swiperWrapperStyle}">
			{#each Array(size) as _, index}
				<div class="swiper-slide {swiperSlideClass}" style=" {swiperSlideStyle}">
					<slot name="slide" {index} />
				</div>
			{/each}
		</div>
		{#if hasPagination}
			<div class="swiper-pagination {swiperPaginationClass}" style=" {swiperPaginationStyle}"></div>
		{/if}

		{#if hasControlBtns}
			<div class="swiper-button-prev {swiperPrevBtnClass}" style=" {swiperPrevBtnStyle}"></div>
			<div class="swiper-button-next {swiperNextBtnClass}" style=" {swiperNextBtnStyle}"></div>
		{/if}

		{#if hasScrollbar}
			<div class="swiper-scrollbar {swiperScrollbarClass}" style=" {swiperScrollbarStyle}"></div>
		{/if}
	</div>
</EasyScriptLoader>
