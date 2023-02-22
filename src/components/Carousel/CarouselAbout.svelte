<script lang="ts">
	import circle from "../../assets/circle.png";
	import bg from "../../assets/bg.png";

	type ImageType = {
		title: string,
		src: string
	}
	export let images: ImageType[];
</script>

<ul class={`flex overflow-x-auto snap-x gap-2`}>
	{#each images as {title, src}}
	<li class="shrink-0 snap-center ml-3 border rounded-[25px] overflow-hidden relative flex justify-center">
		<img src={bg} alt={title} class="h-56 w-36"/>
		<img src={circle} alt="circle" class="h-[40%] w-[55%] absolute top-[20%]"/>
		<span class="absolute text-white top-[70%]">Muta Festival</span>
	</li>
	{/each}
</ul>