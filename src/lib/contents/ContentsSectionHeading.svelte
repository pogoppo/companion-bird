<script lang="ts">
	export let sectionNumber: number;
	export let name: string;
	export let nameSub: string;

	const displaySectionNumber = String(sectionNumber + 1).padStart(2, '0');
</script>

<h1 class="ContentsSectionHeading" data-number={displaySectionNumber}>
	{name}
	<span class="ContentsSectionHeading__sub">{nameSub}</span>
</h1>

<style lang="scss">
	@use 'src/lib/scss/responsive.scss';

	.ContentsSectionHeading {
		display: flex;
		flex-direction: column;
		position: relative;
		width: max-content;
		margin: 0;
		margin-bottom: 16px;
		padding-left: 64px;
		font-size: 2rem;
		font-weight: lighter;
		@include responsive.mq(L) {
			margin-bottom: 4vh;
			padding-left: 12vw;
			font-size: 5vw;
		}
		&__sub {
			align-self: flex-end;
			margin-top: -8px;
			margin-right: 0.5em;
			font-style: italic;
			font-size: 0.9rem;
			opacity: 0.8;
			@include responsive.mq(L) {
				margin-top: -1vw;
				font-size: 2vw;
			}
		}
		&::before {
			content: attr(data-number) '.';
			position: absolute;
			top: 0;
			left: 0;
			color: var(--accent-color);
			font-size: 3rem;
			line-height: 1;
			mix-blend-mode: multiply;
			@include responsive.mq(L) {
				font-size: 8vw;
			}
		}
	}
</style>
