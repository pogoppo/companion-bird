<script lang="ts">
	import ContentsSection from '$lib/contents/ContentsSection.svelte';
	export let sectionNumber: number;
</script>

<ContentsSection
	{sectionNumber}
	layout="reverse"
	name="コンゴウインコ"
	nameSub="Macaw"
	artImageFileName="Ara-macao.png"
	mapImageFileName="SA-North.png"
	mapLabel="原産地: 南アメリカ"
	--contents-background-color="rgb(237 244 218 / 50%)"
>
	<p>
		南アメリカの熱帯雨林地帯が原産地で、標高1,000 ~
		3,000フィートの湿度の高い常緑樹林に生息しています。
	</p>
	<p>
		この種は自然界に広く生息していたが、森林伐採やペット売買のための違法な捕獲により、多くの地域で絶滅の危機に瀕しています。
	</p>
	<p>
		野生ではコンゴウインコは小さな群れで生活しています。
		単独でペットとして飼う場合、あなたはこの鳥の群れの仲間になり、強い絆を築くことができます。
		コンゴウインコと暮らすには毎日気を配り、触れ合うことが必要です。
		適切な訓練と社会化を行わないと、攻撃的で破壊的な性格になることがあります。
	</p>
	<p>
		コンゴウインコの印象的な大きなくちばしは強力で、刺激すると噛むことがあります。
		この鳥は、鳥の警告サインや境界線を理解できないほど幼い子どものいる家庭にはあまり適さないかもしれません。
	</p>
</ContentsSection>
