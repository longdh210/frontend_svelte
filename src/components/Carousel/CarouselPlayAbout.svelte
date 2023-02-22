<script lang="ts">
	import avt from "../../assets/avt.png";
	import users from "../../assets/users.png"
	import share from "../../assets/share.png";
	type ImageType = {
		title: string,
		src: string
	}
	export let images: ImageType[];
</script>

<ul class={`flex flex-col sm:flex-row overflow-y-auto gap-y-4 sm:gap-0 snap-y snap-mandatory w-full justify-center sm:justify-start`}>
	{#each images as {title, src}}
	<li class="shrink-0 snap-center w-[100%] sm:w-[50%] p-5 sm:p-0 sm:ml-3">
		<div class={`h-[100%] w-[100%] sm:w-[100%] sm:h-[90%] border rounded-lg sm:overflow-hidden`}>
			<img {title} {src} alt={title} class={`h-32 w-full`}/>
			<div class="h-[60%] w-full relative ml-3 flex flex-row mt-5 sm:mt-0">
				<div class="h-[100%] w-[20%] flex items-center mr-2">
					<img class="w-[80%] border border-orange-400 rounded-[20px] sm:mb-10" src={avt} alt="avt"/>
				</div>
				<div class="h-[100%] w-[40%] flex flex-col justify-center">
					<span class="text-black font-bold">Enjoy learning English!</span>
					<span>9/1 15:01 ~ 9/1 16:00</span>
					<span class="block sm:mb-8">English</span>
				</div>
				<div class="h-[100%] w-[30%] flex items-end justify-center flex-col">
					<img class="w-[15%] mr-3 mb-1" src={share} alt="share"/>
					<span class="border-2 rounded-[10px] p-1 mb-10">ifme</span>
				</div>
			</div>
		</div>
	</li>
	{/each}
</ul>