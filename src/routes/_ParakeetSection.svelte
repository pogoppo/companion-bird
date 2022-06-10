<script lang="ts">
	import ContentsSection from '$lib/contents/ContentsSection.svelte';
	export let sectionNumber: number;
</script>

<ContentsSection
	{sectionNumber}
	layout="normal"
	name="セキセイインコ"
	nameSub="Budgie"
	artImageFileName="Melopsittacus-undulatus.png"
	mapImageFileName="AU.png"
	mapLabel="原産地: オーストラリア全域"
	--contents-background-color="rgb(235 227 209 / 50%)"
>
	<p>
		セキセイインコはオーストラリア原産で、現在でも草原に大きな群れをなして生息しています。
		しかし、これらの野生種は、ペットショップで普通に見られるセキセイインコよりもやや小型です。
	</p>
	<p>
		ペットとして一般的なセキセイインコには、米国種と英国種の2種類がいます。
		ペットショップでよく見かけるのは米国種で、展示会やショーでよく見かけるのは大型の英国種です。
		英国種は米国種とは外見が異なりますが、どちらも同じ種類に属します。
	</p>
	<p>
		セキセイインコは穏やかでおとなしい鳥です。また、幼少期に飼いならした場合、非常に飼いやすい鳥です。
		しかし、ペアの場合、飼い主に懐かなかったりおしゃべりをしなかったりといった事があります。
	</p>
</ContentsSection>
