<script lang="ts">
	import { onMount } from 'svelte';
	import gsap from 'gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';
	import Fa from 'svelte-fa/src/fa.svelte';
	import { faAnglesDown } from '@fortawesome/free-solid-svg-icons';

	import Header from '$lib/header/Header.svelte';

	gsap.registerPlugin(ScrollTrigger);

	let splashScreenElement: HTMLElement;

	onMount(() => {
		const splashTimeline = gsap.timeline({
			scrollTrigger: {
				trigger: `.SplashScreen__anchor`,
				start: `top 0%`,
				end: `bottom 25%`,
				scrub: true
			}
		});
		splashTimeline.to(splashScreenElement, {
			opacity: 1,
			ease: 'none'
		});
		splashTimeline.to(splashScreenElement, {
			opacity: 0.75,
			ease: 'none'
		});
		splashTimeline.to(splashScreenElement, {
			opacity: 0,
			ease: 'none',
			pointerEvents: 'none'
		});

		ScrollTrigger.refresh();
	});
</script>

<div class="SplashScreen">
	<div class="SplashScreen__anchor" />

	<div class="SplashScreen__body" bind:this={splashScreenElement}>
		<Header />

		<section class="SplashScreenSection">
			<img
				src={`${import.meta.env.VITE_IMAGE_PATH_BASE}/J.G.Keulemans.png`}
				alt="J.G.キューレマンス"
				class="SplashScreenSection__title-icon"
			/>
			<h1 class="SplashScreenSection__title">
				{import.meta.env.VITE_SITE_TITLE}
			</h1>
			<p class="SplashScreenSection__description">
				オランダ出身の鳥のイラストレーターであった彼の絵と一緒に、コンパニオンバード（伴侶としての鳥）を見ていきましょう。
			</p>
			<i class="SplashScreenSection__scroll-icon">
				<Fa icon={faAnglesDown} />
			</i>
		</section>
	</div>
</div>

<style lang="scss">
	@use 'src/lib/scss/responsive.scss';

	@keyframes hopping {
		0% {
			transform: translate(0, 0) scaleX(1.25);
		}
		100% {
			transform: translate(0, 16px) scaleX(1.25);
		}
	}
	.SplashScreen {
		&__anchor {
			height: 50vh;
			height: 50dvh;
		}
		&__body {
			position: fixed;
			top: 0;
			z-index: 21;
			width: 100%;
			height: 100vh;
			height: 100dvh;
		}
	}
	.SplashScreenSection {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		position: relative;
		width: 100%;
		height: 100%;
		padding: 32px;
		box-sizing: border-box;
		background-color: #0e4744;
		color: var(--white-color);
	}
	.SplashScreenSection {
		&__title-icon {
			width: 120px;
			height: auto;
		}
		&__title {
			margin: 16px 0;
			font-family: 'Kaisei Opti', serif;
			font-size: 24px;
			font-weight: normal;
			@include responsive.mq(L) {
				font-size: 40px;
			}
		}
		&__description {
			margin-bottom: 32px;
			text-align: center;
			font-size: 0.9rem;
			line-height: 2;
			@include responsive.mq(L) {
				font-size: initial;
			}
		}
		&__scroll-icon {
			font-size: 32px;
			animation-name: hopping;
			animation-duration: 0.5s;
			animation-timing-function: ease-in;
			animation-iteration-count: infinite;
			animation-direction: alternate;
			@include responsive.mq(L) {
				font-size: 40px;
			}
		}
	}
</style>
