<script lang="ts">
	import EasySwiper from '../lib/easy-swiper.svelte';
</script>

<div>
	<EasySwiper size={10}>
		<div slot="slide" let:index>Slide {index}</div>
	</EasySwiper>
</div>

<style>
	:global(.swiper) {
		width: 600px;
		height: 300px;
		border: 1px solid grey;
	}

	:global(.swiper-slide) {
		display: flex;
		align-items: center;
		justify-content: center;
		background-color: aqua;
	}
</style>
