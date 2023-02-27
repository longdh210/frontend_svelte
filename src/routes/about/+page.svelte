<script>
	import "../../app.css";

	import CarouselAbout from "../../components/Carousel/CarouselAbout.svelte";
	import CarouselPlayAbout from "../../components/Carousel/CarouselPlayAbout.svelte";
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

<div class="w-screen h-screen bg-slate-100 flex flex-col md:flex-row">
	<NavBar></NavBar>
	<div class="h-full sm:w-full sm:h-full md:w-[80%] md:h-full lg:w-[60%] lg:h-full bg-white flex-none flex-col sm:overflow-hidden">
		<div class="mt-1 w-full h-[30%] flex flex-col">
			<span class="float-left mt-2 mb-5 ml-3 font-bold">Fun & Enjoy</span>
			<CarouselAbout {images} ></CarouselAbout>
		</div>
		<div class="mt-1 w-full h-[30%] flex flex-col">
			<span class="float-left mt-2 mb-5 ml-3 font-bold">Campus</span>
			<CarouselAbout {images} ></CarouselAbout>
		</div>
		<div class="mt-1 w-full flex flex-col">
			<span class="float-left mt-2 mb-5 ml-3 font-bold">Let's play</span>
			<CarouselPlayAbout {images}></CarouselPlayAbout>
		</div>
	</div>
</div>
