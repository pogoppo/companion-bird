<script lang="ts">
	export let name: string;
	export let artImagePath: string;
</script>

<figure class="ContentsSectionArt">
	<img class="ContentsSectionArt__image" src={artImagePath} alt={name} />
</figure>

<style lang="scss">
	.ContentsSectionArt {
		display: flex;
		justify-content: flex-end;
		margin: 0;
		&__image {
			display: block;
			width: 100%;
			max-width: 960px;
			height: auto;
			margin: var(--contents-art-margin, 0);
			object-fit: cover;
			object-position: top center;
		}
	}
</style>
