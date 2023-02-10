<script>
	import "../../app.css";
	import bell from "../../assets/bell.png";
	import megaphone from "../../assets/megaphone.png";
	import search from "../../assets/search.png";
	import person from "../../assets/person.png";
	import gamepad from "../../assets/gamepad.png";
	import users from "../../assets/users.png";
	import paperPlane from "../../assets/paper-plane.png";
	import Carousel from '../../components/Carousel/Carousel.svelte'
	
	let images = [
		{title: 'London', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'HCM city', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Da Nang', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Can Tho', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Ca Mau', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Rach Gia', src: 'https://picsum.photos/800/600?random=2'},
	]
</script>

<div class="w-screen h-screen bg-sky-300 flex justify-center items-center">
	<div class="sm:w-full sm:h-full lg:w-2/6 lg:h-3/4 bg-white flex-none flex-col border rounded-lg overflow-y-scroll">
		<div class="bg-slate-200 h-[10%]">
			<div class="float-left">
				<h1 class="font-title font-bold text-fuchsia-500 text-4xl mt-2 ml-3">ifland</h1>
			</div>
			<div class="flex flex-row float-right mt-3 mr-3">
			  <img class="w-8 h-8 mr-3"
				src={megaphone}
				alt="bell"
			  />
			  <img class="w-8 h-8 mr-3"
				src={bell}
				alt="megaphone"
			  />
			  <img class="w-8 h-8"
				src={search}
				alt="search"
			  />
			</div>
		  	</div>
		  	<div class="w-full h-1/3 bg-slate-200 flex items-center flex-col relative border rounded-b-[50px]">
				<div class="w-1/2">
					<img class="w-5/6 h-5/6" src={person} alt="person"/>
				</div>
				<div class="w-5/6 h-14 bg-white border rounded-lg absolute -bottom-7 flex items-center justify-center">
					<div class="mr-5">
						<img class="w-10 h-10 inline-block mr-2" src={gamepad} alt="gamepad"/>
						<span class="text-cyan-300 font-bold">Lounge ></span>
					</div>
					<span>|</span>
					<div class="flex flex-row float-right ml-5">
						<img class="w-8 h-8 mr-2" src={users} alt="users"/>
						<img class="w-8 h-8" src={paperPlane} alt="paper plane"/>
					</div>
				</div>
			</div>
			<div class="mt-10 w-full h-2/5 flex flex-col">
				<span class="float-left mt-2 mb-5 ml-3 font-bold">Popular land</span>
				<Carousel {images} width=100 gap=32></Carousel>
			</div>
			<div class="mt-10 w-full h-1/6 flex flex-col items-center">
				<img class="w-[90%] h-[100%]" src="https://picsum.photos/800/600?random=3" alt="adver"/>
			</div>
			<div class="mt-10 w-full h-2/5 flex flex-col">
				<span class="float-left mt-2 mb-5 ml-3 font-bold">Special land</span>
				<Carousel {images} width=250 gap=32></Carousel>
			</div>
	</div>
</div>
