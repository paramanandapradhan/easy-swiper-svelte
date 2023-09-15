# easy-script-loader-svelte

Simple way to load and use swipper js.

# Install 

```
npm i @cloudparker/easy-swiper-svelte --save-dev
```

# Screenshot

<img src="https://raw.githubusercontent.com/paramanandapradhan/easy-swiper-svelte/main/static/easy-swiper-svelte.png.webp" alt="Screenshot" width="300">

# Usage

```ts
<script lang="ts">
	import EasySwiper from '@cloudparker/easy-swiper-svelte';
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


```

