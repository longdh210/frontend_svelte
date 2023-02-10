<script lang="ts">
	import avt from "../../assets/avt.png";
	import users from "../../assets/users.png"
	type ImageType = {
		title: string,
		src: string
	}
	export let images: ImageType[];
	export let width: number;
	export let gap: number;
</script>

<ul class="flex overflow-x-auto gap-{gap} snap-x snap-mandatory">
	{#each images as {title, src}}
	<li class="shrink-0 snap-center">
		<div class="h-full w-[{width}%] border rounded-lg overflow-hidden ml-2">
			<img {title} {src} alt={title} class="h-[40%] w-full object-cover"/>
			<div class="h-[15%] w-full relative inline-block ml-3">
				<img src={avt} alt="avt" class="h-[220%] w-[50%] bg-slate-400 border rounded-lg absolute top-[-130%]">
			</div>
			<div class="h-full w-full inline-block relative ml-3">
				<span class="text-black">#####</span>
				<div class="h-[10%] w-full flex flex-row">
					<span>Maxim</span>
					<img src={users} alt="users" class="h-[80%] ml-3 mr-1 mt-1" />
					<span>5</span>
				</div>
				<span class="block mt-2">English</span>
			</div>
		</div>
	</li>
	{/each}
</ul>