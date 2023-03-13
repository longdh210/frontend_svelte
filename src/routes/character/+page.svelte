<script>
	import { goto } from "$app/navigation";
	import "../../app.css";
    import person from "../../assets/person.png";
    import CarouselTest from "../../components/Carousel/CarouselTest.svelte";
	import NavBar from "../../components/NavBar/NavBar.svelte";

    let images = [
		{title: 'London', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'HCM city', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Da Nang', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Can Tho', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Ca Mau', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Rach Gia', src: 'https://picsum.photos/800/600?random=2'},
	]
</script>

<div class="w-screen h-screen bg-slate-200 flex flex-col md:flex-row">
    <NavBar></NavBar>
	<div class="h-full sm:w-full sm:h-full lg:w-[60%] lg:h-full bg-white flex-none flex-col overflow-y-hidden">
        <div class="w-full h-[15%] flex items-end justify-center">
            <span class="text-xl">Choose an if-me</span>
        </div>
        <div class="w-full h-[40%] flex justify-center items-end">
            <img class="h-[80%]" src={person} alt="person">
        </div>
        <div class="w-full h-[15%]">
            <CarouselTest {images}></CarouselTest>
        </div>
        <div class="w-full h-[15%] flex flex-col items-center">
            <span class="text-xl">Enter nickname</span>
            <input class="border border-b-2 border-t-0 border-l-0 border-r-0 w-[85%]"/>
        </div>
        <div class="w-full h-[15%] flex flex-col items-center">
            <button class="w-[80%] h-[40%] border border-slate-400 rounded-lg hover:bg-gray-200">
                Create your own if-me
            </button>
            <button class="w-[80%] h-[40%] mt-2 border border-slate-400 rounded-lg hover:bg-gray-200 bg-violet-500 text-white"
            on:click={() => {goto("/play")}}
            >
                Start ifland
            </button>
        </div>
	</div>
</div>
