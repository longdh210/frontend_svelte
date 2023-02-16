<script lang="ts">
	import avt from "../../assets/avt.png";
	import users from "../../assets/users.png"
	type ImageType = {
		title: string,
		src: string
	}
	export let images: ImageType[];
	function onClick() {
		console.log("log")
	};
</script>

<ul class="flex overflow-x-auto snap-x gap-6">
	{#each images as {title, src}}
	<li class="shrink-0 snap-center w-[20%] h-[85px]" on:click={() => onClick}>
		<img {title} {src} alt={title}/>
	</li>
	{/each}
</ul>