<script lang="ts">
	export let mapImagePath: string;
	export let mapLabel: string;
</script>

<figure class="ContentsSectionMap">
	<img class="ContentsSectionMap__image" src={mapImagePath} alt={mapLabel} />
	<figcaption class="ContentsSectionMap__label">{mapLabel}</figcaption>
</figure>

<style lang="scss">
	@use 'src/lib/scss/responsive.scss';

	.ContentsSectionMap {
		display: block;
		position: relative;
		float: right;
		margin: 8px;
		@include responsive.mq(L) {
			margin: 32px;
		}
		&__image {
			display: block;
			width: 40vw;
			height: auto;
			@include responsive.mq(L) {
				width: 20vw;
				height: auto;
			}
		}
		&__label {
			display: block;
			margin-top: 8px;
			padding: 0.25em 0.5em;
			background-color: rgba(0, 0, 0, 0.9);
			color: var(--white-color);
			font-size: 0.75rem;
			@include responsive.mq(L) {
				position: absolute;
				bottom: 0;
				left: 0;
				margin-top: 0;
				padding: 0.5em;
				font-size: 1vw;
			}
		}
	}
</style>
