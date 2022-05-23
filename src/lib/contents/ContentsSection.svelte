<script lang="ts">
	import ContentsSectionHeading from '$lib/contents/ContentsSectionHeading.svelte';
	import ContentsSectionMap from '$lib/contents/ContentsSectionMap.svelte';
	import ContentsSectionArt from '$lib/contents/ContentsSectionArt.svelte';

	export let sectionNumber: number;
	export let layout: string = 'normal';
	export let name: string;
	export let nameSub: string;
	export let artImagePath: string;
	export let mapImagePath: string;
	export let mapLabel: string;
</script>

<section class="ContentsSection" data-layout={layout}>
	<div class="ContentsSection__art">
		<ContentsSectionArt {artImagePath} {name} />
	</div>

	<div class="ContentsSection__article">
		<ContentsSectionHeading {sectionNumber} {name} {nameSub} />

		<div class="ContentsSection__body">
			<ContentsSectionMap {mapImagePath} {mapLabel} />

			<slot />
		</div>
	</div>
</section>

<style lang="scss">
	@use 'src/lib/scss/responsive.scss';

	.ContentsSection {
		overflow: hidden;
		position: relative;
		width: 100%;
		height: 100%;
		background-color: var(--contents-background-color, #fff);
		&::before {
			content: '';
			display: block;
			position: absolute;
			z-index: 4;
			width: 100%;
			height: 100%;
			background-image: url('images/background-paper.jpg');
			mix-blend-mode: darken;
			pointer-events: none;
		}
		@include responsive.mq(L) {
			display: grid;
			&[data-layout='normal'] {
				grid-template-areas: '. . .' 'art article .';
				grid-template-rows: 64px calc(100% - 64px);
				grid-template-columns: 50% 1fr 64px;
			}
			&[data-layout='reverse'] {
				grid-template-areas: '. . .' '. article art';
				grid-template-rows: 64px calc(100% - 64px);
				grid-template-columns: 64px 1fr 50%;
			}
		}
	}

	.ContentsSection {
		&__art {
			position: absolute;
			top: 0;
			@include responsive.mq(L) {
				grid-area: art;
				position: static;
			}
		}
		&__article {
			position: absolute;
			bottom: 0;
			z-index: 2;
			padding: 16px;
			background: linear-gradient(
					0deg,
					var(--contents-background-color),
					var(--contents-background-color)
				),
				linear-gradient(0deg, var(--contents-background-color), var(--contents-background-color));
			@include responsive.mq(L) {
				display: flex;
				flex-direction: column;
				justify-content: center;
				grid-area: article;
				position: static;
				max-width: 960px;
				padding: 0;
				background: none;
			}
		}

		&__body {
			> :global(p) {
				margin: 0;
				font-size: 0.75rem;
				@include responsive.mq(L) {
					margin-bottom: 4vh;
					font-size: 1vw;
				}
				&:not(:last-child) {
					margin-bottom: 16px;
				}
			}
		}
	}
</style>
