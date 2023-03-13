<script lang="ts">
    type ImageType = {
		title: string,
		src: string
	}
	export let images: ImageType[];
</script>

<ul class="flex overflow-x-auto snap-x gap-6">
	{#each images as {title, src}}
	<li class="shrink-0 snap-center w-[25%] h-[50%] shadow-sm">
        <div class="border-1 rounded-[25px] overflow-hidden">
            <img class="h-28 w-full" {title} {src} alt={title}/>
            <div class="h-20 w-full flex justify-center items-center bg-white hover:bg-indigo-600 hover:text-white">
                <span>FLO LAND</span>
            </div>
        </div>
	</li>
	{/each}
</ul>