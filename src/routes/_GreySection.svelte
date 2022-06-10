<script lang="ts">
	import ContentsSection from '$lib/contents/ContentsSection.svelte';
	export let sectionNumber: number;
</script>

<ContentsSection
	{sectionNumber}
	layout="reverse"
	name="ヨウム"
	nameSub="Grey Parrot"
	artImageFileName="Psittacus-erithacus.png"
	mapImageFileName="ZA-Congo.png"
	mapLabel="原産地: アフリカ西海岸"
	--contents-background-color="rgb(241 241 241 / 50%)"
>
	<p>
		カメルーン、コンゴ、ガーナ、ケニアなどアフリカの赤道付近に原産地があります。
		生息地は密林ですが、森林の端やサバンナでもよく見られます。
	</p>
	<p>
		ヨウムはコンパニオンバードの中でも知能の高い種類です。
		飼い主に対して非常に甘く愛情深い性格に育つものが多く、かなり社交的な種として知られています。
	</p>
	<p>
		発声と音を聞き分けるのも得意で、幼児の子供と同じように、聞いたことを繰り返す事を好みます。
		キーキーと鳴るドア、車のバックチャイム、火災報知器、電子レンジの警告ベル、電話の着信音など、好きな音を拾って繰り返すことに長けています。
		なので、飼い主は愛鳥が聞く音に注意する必要があります。
		なぜなら、一度覚えたこれらの音を忘れさせることは困難か不可能だからです。
	</p>
</ContentsSection>
