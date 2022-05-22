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
	.ContentsSection {
		display: grid;
		overflow: hidden;
		position: relative;
		width: 100%;
		height: 100%;
		background-color: var(--contents-background-color, #fff);
		&[data-layout='normal'] {
			grid-template-areas: '. .' 'art article';
			grid-template-rows: 64px calc(100% - 64px);
			grid-template-columns: 50% 50%;
		}
		&[data-layout='reverse'] {
			grid-template-areas: '. .' 'article art';
			grid-template-rows: 64px calc(100% - 64px);
			grid-template-columns: 50% 50%;
		}
		&::before {
			content: '';
			display: block;
			position: absolute;
			z-index: 2;
			width: 100%;
			height: 100%;
			background-image: url('images/background-paper.jpg');
			mix-blend-mode: darken;
			pointer-events: none;
		}
	}

	.ContentsSection {
		&__art {
			grid-area: art;
		}
		&__article {
			display: flex;
			flex-direction: column;
			justify-content: center;
			grid-area: article;
			width: 100%;
			max-width: 960px;
			box-sizing: border-box;
		}
		&[data-layout='normal'] &__article {
			padding-right: 64px;
		}
		&[data-layout='reverse'] &__article {
			padding-left: 64px;
		}

		&__body {
			&::after {
				content: '';
				display: block;
				clear: both;
			}
			> :global(p) {
				margin: 0;
				margin-bottom: 4vh;
				font-size: 1vw;
			}
		}
	}
</style>
