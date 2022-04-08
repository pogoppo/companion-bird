<script context="module" lang="ts">
	export const prerender = true;
</script>

<script lang="ts">
	export let sectionNumber: number;
	export let layout: string = 'normal';
	export let nameJA: string;
	export let nameEN: string;
	export let artImagePath: string;
	export let mapImagePath: string;
	export let mapLabel: string;

	const displaySectionNumber = String(sectionNumber + 1).padStart(2, '0');
</script>

<section class="ContentsSection" data-layout={layout}>
	<figure class="ContentsSection__art">
		<img src={artImagePath} alt={nameJA} />
	</figure>

	<div class="ContentsSection__article">
		<h1 class="ContentsSection__heading" data-number={displaySectionNumber}>
			{nameJA}
			<span>{nameEN}</span>
		</h1>

		<div class="ContentsSection__body">
			<figure class="ContentsSection__map">
				<img src={mapImagePath} alt={mapLabel} />
				<figcaption>{mapLabel}</figcaption>
			</figure>

			<slot />
		</div>
	</div>
</section>

<style lang="scss">
	.ContentsSection {
		display: grid;
		overflow: hidden;
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
			display: flex;
			justify-content: flex-end;
			grid-area: art;
			margin: 0;
			> img {
				display: block;
				width: 100%;
				max-width: 960px;
				height: auto;
				margin: var(--contents-art-margin, 0);
				object-fit: cover;
				object-position: top center;
			}
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

		&__heading {
			display: flex;
			flex-direction: column;
			position: relative;
			width: max-content;
			margin: 0;
			margin-bottom: 4vh;
			padding-left: 12vw;
			font-size: 5vw;
			font-weight: lighter;
			> span {
				align-self: flex-end;
				margin-top: -1vw;
				margin-right: 0.5em;
				font-style: italic;
				font-size: 2vw;
				opacity: 0.8;
			}
			&::before {
				content: attr(data-number) '.';
				position: absolute;
				top: 0;
				left: 0;
				color: var(--accent-color);
				font-size: 8vw;
				line-height: 1;
				mix-blend-mode: multiply;
			}
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

		&__map {
			display: block;
			position: relative;
			float: right;
			> img {
				display: block;
				width: 20vw;
				height: auto;
			}
			> figcaption {
				display: block;
				position: absolute;
				bottom: 0;
				left: 0;
				padding: 0.5em;
				background-color: rgba(0, 0, 0, 0.9);
				color: #fff;
			}
		}
	}
</style>
