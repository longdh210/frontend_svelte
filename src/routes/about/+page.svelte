<script>
	import "../../app.css";
	import home from "../../assets/home.png";
	import star from "../../assets/star.png";
	import vest from "../../assets/vest.png";
	import user from "../../assets/user.png";
	import menu from "../../assets/menu.png";
	import add from "../../assets/add.png";

	import CarouselAbout from "../../components/Carousel/CarouselAbout.svelte";
	import CarouselPlayAbout from "../../components/Carousel/CarouselPlayAbout.svelte";

	let images = [
		{title: 'London', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'HCM city', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Da Nang', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Can Tho', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Ca Mau', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Rach Gia', src: 'https://picsum.photos/800/600?random=2'},
	]
	let menuBar = false;
</script>

<div class="w-screen h-screen bg-slate-100 flex flex-col md:flex-row">
	<div class="w-full h-full flex justify-end text-end mr-2 sm:w-full mt-2">
		<nav class="h-[10%]">
			<div class="w-full cursor-pointer md:hidden flex justify-end px-4 border-r-4 border-slate-100 mb-2 mt-2">
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<img class="w-[5%] sm:w-[3%]" src={menu} alt="menu" on:click={() => menuBar = !menuBar}/>
			</div>
		  <ul class="{menuBar == true ? "" : "hidden"} md:block">
			<li class="mb-2">
			  <a class="px-4 border-r-4 border-amber-500 flex items-center justify-end" href="/">
				<span>Home</span>
				<img class="w-[3%] md:w-[15%] lg:w-[5%] xl:w-[3%] inline-block ml-2" src={home} alt="home"/>
			  </a>
			</li>
			<li class="mb-2">
			  <a class="px-4 border-r-4 border-slate-100 flex items-center justify-end" href="/about">
				<span>About</span>
				<img class="w-[3%] md:w-[15%] lg:w-[5%] xl:w-[3%] inline-block ml-2" src={star} alt="About"/>
			  </a>
			</li>
			<li class="mb-2">
				<a class="px-4 border-r-4 border-slate-100 flex items-center justify-end" href="/add">
				  <span>Add</span>
				  <img class="w-[3%] md:w-[15%] lg:w-[5%] xl:w-[3%] inline-block ml-2" src={add} alt="Add"/>
				</a>
			</li>
			<li class="mb-2">
			  <a class="px-4 border-r-4 border-slate-100 flex items-center justify-end" href="/character">
				<span>Character</span>
				<img class="w-[3%] md:w-[15%] lg:w-[5%] xl:w-[3%] inline-block ml-2" src={vest} alt="vest"/>
			  </a>
			</li>
			<li class="mb-2">
				<a class="px-4 border-r-4 border-slate-100 flex items-center justify-end" href="/profile">
				  <span>Profile</span>
				  <img class="w-[3%] md:w-[15%] lg:w-[5%] xl:w-[3%] inline-block ml-2" src={user} alt="user"/>
				</a>
			  </li>
		  </ul>
		</nav>
	  </div>
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
