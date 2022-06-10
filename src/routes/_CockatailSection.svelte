<script lang="ts">
	import ContentsSection from '$lib/contents/ContentsSection.svelte';
	export let sectionNumber: number;
</script>

<ContentsSection
	{sectionNumber}
	layout="normal"
	name="オカメインコ"
	nameSub="Cockatail"
	artImageFileName="Nymphicus-hollandicus.png"
	mapImageFileName="AU.png"
	mapLabel="原産地: オーストラリア全域"
	--contents-background-color="rgb(245 230 216 / 50%)"
>
	<p>
		原産地はオーストラリアで、主にアウトバック、大陸北部の地域に住んでいます。
		1770年に発見されたオカメインコは、オーストラリアに住むキバタンに代表される白色オウム系列の中で最も小さなメンバーです。
		白色オウムと同じような特徴や習性を多く持ち、野生では大きな群れで生活しています。
	</p>
	<p>
		オカメインコは1900年代にペットとして人気を博しました。
		飼育下で繁殖しやすく、そのおとなしい、フレンドリーな性格は、人間との生活にも自然にフィットするようになります。
	</p>
	<p>
		オカメインコは知的な鳥で、時間をかけてさまざまな芸を覚えることができます。
		手を振ったり、口笛を吹いたり、鈴を鳴らしたりといった具合です。賢い小鳥なので、新しい挑戦を楽しむことができます。
		多くのオカメインコは、鏡の中の「もう一羽の鳥」に話しかけて何時間も自分を飽きさせないようにすることさえあります。
	</p>
</ContentsSection>
