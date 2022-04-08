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
</style>
