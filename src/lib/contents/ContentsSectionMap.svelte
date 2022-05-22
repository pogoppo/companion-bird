<script lang="ts">
	export let mapImagePath: string;
	export let mapLabel: string;
</script>

<figure class="ContentsSectionMap">
	<img class="ContentsSectionMap__image" src={mapImagePath} alt={mapLabel} />
	<figcaption class="ContentsSectionMap__label">{mapLabel}</figcaption>
</figure>

<style lang="scss">
	.ContentsSectionMap {
		display: block;
		position: relative;
		float: right;
		&__image {
			display: block;
			width: 20vw;
			height: auto;
		}
		&__label {
			display: block;
			position: absolute;
			bottom: 0;
			left: 0;
			padding: 0.5em;
			background-color: rgba(0, 0, 0, 0.9);
			color: var(--white-color);
		}
	}
</style>
