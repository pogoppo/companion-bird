<script lang="ts">
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section class="ContentsSection">
	<figure class="ContentsSection__art">
		<img
			src="images/zoological-arts/Melopsittacus-undulatus.png"
			alt="John Gerrard Keulemans - Melopsittacus undulatus (1869)"
		/>
	</figure>
	<div class="ContentsSection__article">
		<h1 class="ContentsSection__heading" data-number="01">
			セキセイインコ
			<span>Parakeet / Budgie</span>
		</h1>
		<div class="ContentsSection__body">
			<figure class="ContentsSection__map">
				<img src="images/maps/AU.png" alt="オーストラリア" />
				<figcaption>原産地: オーストラリア全域</figcaption>
			</figure>
			<p>
				何はほかどうしてもこういう活動通りというのの時が通っなです。
				おおかた結果が抑圧者もすでにこの支配ませませまでが進まからいませのは附随云えたたて、まだにも進んないなけれだまし。
				勇気がしますのはひょろひょろ今日をけっしてですたべく。
			</p>
			<p>
				何はほかどうしてもこういう活動通りというのの時が通っなです。
				おおかた結果が抑圧者もすでにこの支配ませませまでが進まからいませのは附随云えたたて、まだにも進んないなけれだまし。
				勇気がしますのはひょろひょろ今日をけっしてですたべく。
			</p>
			<p>
				何はほかどうしてもこういう活動通りというのの時が通っなです。
				おおかた結果が抑圧者もすでにこの支配ませませまでが進まからいませのは附随云えたたて、まだにも進んないなけれだまし。
				勇気がしますのはひょろひょろ今日をけっしてですたべく。
			</p>
		</div>
	</div>
</section>

<style lang="scss">
	.ContentsSection {
		display: grid;
		grid-template-areas: '. .' 'art article';
		grid-template-rows: 64px calc(100vh - 64px);
		grid-template-columns: 50vw 50vw;
		overflow: hidden;
		background-image: linear-gradient(rgb(248, 238, 212, 0.5), rgb(248, 238, 212, 0.5)),
			url('images/background-paper.jpg');
		background-blend-mode: multiply, normal;
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
				margin-top: -8vw;
				margin-left: 0vw;
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
			padding-right: 64px;
			box-sizing: border-box;
		}
		&__heading {
			display: inline-flex;
			flex-direction: column;
			position: relative;
			margin: 0;
			margin-bottom: 4vh;
			padding-left: 10vw;
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
			> p {
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
