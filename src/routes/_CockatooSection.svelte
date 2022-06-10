<script lang="ts">
	import ContentsSection from '$lib/contents/ContentsSection.svelte';
	export let sectionNumber: number;
</script>

<ContentsSection
	{sectionNumber}
	layout="normal"
	name="キバタン"
	nameSub="Cockatoo"
	artImageFileName="Cacatua-galerita-triton.png"
	mapImageFileName="AU-coast.png"
	mapLabel="原産地: オーストラリア沿岸"
	--contents-background-color="rgb(238 236 216 / 50%)"
>
	<p>
		オーストラリア東部、ニューギニア、インドネシア、ニュージーランドに生息しており、熱帯・亜熱帯雨林を住処にしています。
		また、都市部でもよく見かけ、オーストラリアの一部の地域では多く生息しているため、人々はこの鳥を害鳥として捉える人も少なくないようです。
	</p>
	<p>
		インコやオウムは言葉を含め、音を模倣することが得意ですが、キバタンに関して言えば発声能力は少し劣っていると言えます。
		しかし、語彙の多さについては飼い主の努力次第で幅広く学習させる事ができます。
	</p>
	<p>
		キバタンの中には、覚えた言葉を叫んでしまう子もいるので注意が必要です。
		この傾向は飼い主をイライラさせることがあり、ご近所や来客とのトラブルの原因になることもあります。
	</p>
</ContentsSection>
