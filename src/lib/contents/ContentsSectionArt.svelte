<script lang="ts">
	export let name: string;
	export let artImageFileName: string;
	const imagePath1920w = `${
		import.meta.env.VITE_IMAGE_PATH_BASE
	}/zoological-arts/1920w-${artImageFileName}`;
	const imagePath480w = `${
		import.meta.env.VITE_IMAGE_PATH_BASE
	}/zoological-arts/480w-${artImageFileName}`;
</script>

<figure class="ContentsSectionArt">
	<img
		class="ContentsSectionArt__image"
		srcset="{imagePath1920w} 1920w, {imagePath480w} 480w"
		sizes="100%"
		src={imagePath1920w}
		alt={name}
	/>
</figure>

<style lang="scss">
	@use 'src/lib/scss/responsive.scss';

	.ContentsSectionArt {
		display: flex;
		justify-content: flex-end;
		margin: 0;
		&__image {
			display: block;
			width: 960px;
			max-width: 100%;
			height: auto;
			margin-top: -24px;
			object-fit: cover;
			object-position: top center;
			@include responsive.mq(L) {
				margin-top: -64px;
			}
		}
	}
</style>
