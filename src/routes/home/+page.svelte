<script>
	import "../../app.css";
	import bell from "../../assets/bell.png";
	import megaphone from "../../assets/megaphone.png";
	import search from "../../assets/search.png";
	import person from "../../assets/person.png";
	import gamepad from "../../assets/gamepad.png";
	import users from "../../assets/users.png";
	import paperPlane from "../../assets/paper-plane.png";
	import comment from "../../assets/comment.png";

	import Carousel from '../../components/Carousel/Carousel.svelte'
	import InforForm from '../../components/Informaton/InforForm.svelte';
	import NavBar from "../../components/NavBar/NavBar.svelte";
	import Notice from "../notice/+page.svelte";
	import { goto } from "$app/navigation";
	
	let images = [
		{title: 'London', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'HCM city', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Da Nang', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Can Tho', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Ca Mau', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Rach Gia', src: 'https://picsum.photos/800/600?random=2'},
	]

	let current = 'global';
</script>

<div class="w-screen h-screen bg-slate-200 flex flex-col md:flex-row">
	<NavBar></NavBar>
	<div class="h-full sm:w-full sm:h-full md:w-[80%] md:h-full lg:w-[60%] lg:h-full bg-white flex-none flex-col overflow-y-scroll overflow-x-hidden border-0">
		<div class="bg-sky-300 h-[10%] border border-sky-300">
			<div class="float-left">
				<h1 class="font-title font-bold text-fuchsia-500 text-4xl mt-2 ml-3">ifland</h1>
			</div>
			<div class="flex flex-row float-right mt-3 mr-3">
			  <!-- svelte-ignore a11y-click-events-have-key-events -->
			  <img class="w-8 h-8 mr-3"
				src={megaphone}
				alt="bell"
				on:click={() => goto("/notice")}
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
		  	<div class="w-full h-[30%] sm:h-[40%] bg-sky-300 flex items-center flex-col relative rounded-b-[50px] border border-sky-300">
				<div class="w-[55%] sm:w-1/2">
					<img class="w-full sm:w-5/6 h-5/6" src={person} alt="person"/>
				</div>
				<div class="w-5/6 h-14 bg-white border rounded-lg absolute -bottom-7 flex items-center justify-center shadow-lg">
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
				<Carousel {images} width=100 gap=44 widthAvt=50 bgWidth=40></Carousel>
			</div>
			<div class="mt-7 w-full h-1/6 flex flex-col items-center">
				<img class="w-[90%] h-[100%]" src="https://picsum.photos/800/600?random=3" alt="adver"/>
			</div>
			<div class="mt-7 w-full h-[50%] flex flex-col">
				<span class="float-left mt-2 mb-5 ml-3 font-bold">Special land</span>
				<Carousel {images} width=200 gap=56  widthAvt=30 bgWidth=50></Carousel>
			</div>
			<div class="mt-7 mb-3 w-full">
				<div class="ml-3">
					<!-- svelte-ignore a11y-click-events-have-key-events -->
					<span class="inline-block font-bold mr-2 {current === 'global' ? 'selected' : ''}" on:click={() => current = 'global'} >	
						Global
					</span>
					<!-- svelte-ignore a11y-click-events-have-key-events -->
					<span class="inline-block font-bold {current === 'my' ? 'selected' : ''}" on:click={() => current = 'my'}>
						My
					</span>
				</div>
				<div class="h-20 w-full flex justify-center items-center">
					<img class="w-[90%] h-[100%] mt-3" src="https://picsum.photos/800/600?random=3" alt="adver"/>
				</div>
				<div class="w-full mt-5">
					{#if current === "global"}
						<InforForm></InforForm>
						<InforForm></InforForm>
						<InforForm></InforForm>
						<InforForm></InforForm> 
					{:else if current === "my"}
						<div class="h-36 w-full flex flex-col justify-center items-center text-center px-2">
							<img class="w-[5%]" src={comment} alt="comment"/>
							<span class="text-slate-400">There is no land that I personally made or registered notification for. Try searching your land you like.</span>
						</div>
					{/if}
				</div>
			</div>
	</div>
</div>

<style>
	.selected {
		color: #8776ef;
		border-bottom: 2px solid #8776ef;
	}
</style>
