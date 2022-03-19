<script context="module" lang="ts">
	import { browser, dev } from '$app/env';
	export const prerender = true;
</script>

<script lang="ts">
	import Header from '$lib/header/Header.svelte';
	import '../app.css';
</script>

<Header />

<main>
	<slot />
</main>

<style lang="scss">
	main {
		display: flex;
		flex-direction: column;
		&::before {
			content: '';
			display: block;
			position: fixed;
			z-index: 8;
			width: 100%;
			height: 64px;
			background-image: url('images/wire.png');
			background-size: contain;
			background-position: center;
		}
	}
</style>
