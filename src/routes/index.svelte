<script lang="ts">
	import { onMount } from 'svelte';
	import gsap from 'gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';

	import ParakeetSection from '$lib/contents/main/ParakeetSection.svelte';
	import GreySection from '$lib/contents/main/GreySection.svelte';
	import CockatailSection from '$lib/contents/main/CockatailSection.svelte';

	gsap.registerPlugin(ScrollTrigger);

	const sectionElements: HTMLElement[] = [];
	const sections = [ParakeetSection, GreySection, CockatailSection];

	onMount(() => {
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
	});
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<div class="MainContents">
	{#each sections as sectionComponent, index}
		<div class="MainContents__anchor" data-index={index} />
		<div
			class="MainContents__section"
			bind:this={sectionElements[index]}
			style:z-index={index * -1}
		>
			<svelte:component this={sectionComponent} sectionNumber={index} />
		</div>
	{/each}
</div>

<style lang="scss">
	.MainContents {
		&::before {
			content: '';
			display: block;
			position: fixed;
			top: 0;
			z-index: 8;
			width: 100%;
			height: 64px;
			background-image: url('images/wire.png');
			background-size: contain;
			background-position: center;
		}
	}

	.MainContents {
		&__anchor {
			height: 100vh;
		}
		&__section {
			position: fixed;
			top: 0;
			z-index: 2;
			width: 100%;
			height: 100vh;
		}
	}
</style>
