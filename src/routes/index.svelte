<script context="module" lang="ts">
	export const prerender = true;
</script>

<script lang="ts">
	import { onMount } from 'svelte';
	import gsap from 'gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';

	import SplashScreen from './_SplashScreen.svelte';
	import ParakeetSection from './_ParakeetSection.svelte';
	import GreySection from './_GreySection.svelte';
	import CockatailSection from './_CockatailSection.svelte';

	gsap.registerPlugin(ScrollTrigger);

	const sectionElements: HTMLElement[] = [];
	const sections = [ParakeetSection, GreySection, CockatailSection];

	onMount(() => {
		window.scrollTo(0, 0);

		sectionElements.forEach((element, index) => {
			const pagingTimeline = gsap.timeline({
				scrollTrigger: {
					trigger: `.MainContents__anchor[data-index="${index}"]`,
					start: `top 0%`,
					end: `bottom 0%`,
					scrub: true
				}
			});
			pagingTimeline.to(element, {
				yPercent: 2,
				opacity: 1,
				ease: 'none'
			});
			pagingTimeline.to(element, {
				yPercent: 5,
				opacity: 0.75,
				ease: 'none'
			});
			pagingTimeline.to(element, {
				yPercent: 20,
				opacity: 0,
				ease: 'none',
				pointerEvents: 'none'
			});
		});

		ScrollTrigger.refresh();
	});
</script>

<svelte:head>
	<title>{import.meta.env.VITE_SITE_TITLE}</title>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="" />
	<link
		href="https://fonts.googleapis.com/css2?family=Noto+Serif+JP:wght@200;400;700&display=swap"
		rel="stylesheet"
	/>
	<link
		href="https://fonts.googleapis.com/css2?family=Kaisei+Opti:wght@700
					&display=swap&text={import.meta.env.VITE_SITE_TITLE}"
		rel="stylesheet"
	/>
</svelte:head>

<SplashScreen />

<div class="MainContents">
	{#each sections as sectionComponent, index}
		<div class="MainContents__anchor" data-index={index} />
		<div
			class="MainContents__section"
			bind:this={sectionElements[index]}
			style:z-index={20 - index}
		>
			<svelte:component this={sectionComponent} sectionNumber={index} />
		</div>
	{/each}
</div>

<style lang="scss">
	@use 'src/lib/scss/responsive.scss';

	.MainContents {
		&::after {
			content: '';
			display: block;
			position: fixed;
			top: 0;
			z-index: 20;
			width: 100%;
			height: 48px;
			background-image: url('images/wire.png');
			background-size: cover;
			background-position: center;
			@include responsive.mq(L) {
				height: 64px;
				background-size: contain;
				background-position: center;
			}
		}
	}

	.MainContents {
		&__anchor {
			height: 100vh;
			height: 100dvh;
		}
		&__section {
			position: fixed;
			top: 0;
			width: 100%;
			height: 100vh;
			height: 100dvh;
		}
	}
</style>
