<script>
	import CarouselAdd from "../../components/Carousel/CarouselAdd.svelte";
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
	<div class="h-full sm:w-full sm:h-full md:w-[80%] md:h-full lg:w-[60%] lg:h-full bg-slate-100 flex-none flex-col overflow-y-scroll overflow-x-hidden border-0">
		<div class="h-[10%] w-full flex flex-col items-center mb-5">
			<h1 class="mt-2 mb-2 text-xl">Create a land</h1>
			<input class="w-[50%] h-[45%] border-2 rounded-lg px-5 bg-slate-100" placeholder="Type the room title! You can meet global users"/>
		</div>
		<div class="h-[25%] w-full mb-10 sm:mb-5 ml-3">
			<CarouselAdd {images}></CarouselAdd>
		</div>
		<div class="h-[10%] w-full ml-3 mb-10 sm:mb-5">
			<div class="flex flex-row justify-between mr-3">
				<h1 class="font-bold">Land's main Language</h1>
				<select class="border-4 border-slate-300 rounded-md mr-3 w-20 px-3" name="language" id="language">
					<option value="en">EN</option>
					<option value="vn">VN</option>
					<option value="kr">KR</option>
					<option value="cn">CN</option>
				</select>
			</div>
			<span>Please select the main language to use in the land</span>
		</div>
		<div class="h-[8%] w-full ml-3 mb-10 sm:mb-5">
			<div class="flex flex-row justify-between">
				<h1 class="font-bold inline-block">time</h1>
				<div class="flex flex-row mr-5">
					<input type="radio" id="time1" name="time" value="30">
					<label class="ml-1 mr-3" for="time1">Start now</label><br>
					<input type="radio" id="time2" name="time" value="60">
					<label class="ml-1" for="time2">Reserve</label><br>  
				</div>
			</div>
		</div>
		<div class="h-[10%] w-full ml-3 mb-10 sm:mb-5">
			<div class="flex flex-row justify-between mr-3">
				<h1 class="font-bold">tag</h1>
				<select class="mr-4 bg-slate-100" name="tags" id="tags">
					<option value="1">not set</option>
					<option value="2">tag 1</option>
					<option value="3">tag 2</option>
					<option value="4">tag 3</option>
				</select>
			</div>
			<span>Select tag</span>
		</div>
		<div class="h-[10%] w-full ml-3 mb-6 sm:mb-5">
			<div class="flex flex-row justify-between mr-3">
				<h1 class="font-bold">public</h1>
				<label class="switch mr-5">
					<input type="checkbox">
					<span class="slider round"></span>
				</label>
			</div>
			<span>Setting the Land as public enables anyone to enter freely</span>
		</div>
		<div class="flex justify-center mb-6 sm:mb-2">
			<span class="w-[90%] border border-b-2 "></span>
		</div>
		<div class="h-[10%] w-full ml-3 mb-6 sm:mb-5">
			<div class="flex flex-row justify-between mr-3 ">
				<div>
					<h1 class="font-bold inline-block">Everyone is if-me</h1>
					<span class="border rounded-[20px] bg-indigo-600 p-1 text-white">Beta</span>
				</div>
				<label class="switch mr-5">
					<input type="checkbox">
					<span class="slider round"></span>
				</label>
			</div>
			<span>If you select "Everyone is if-me." all participants appear as if-me</span>
		</div>
		<div class="flex justify-center mb-6 sm:mb-5">
			<button class="h-10 w-[60%] border rounded-lg bg-slate-300 hover:bg-indigo-600 hover:text-white">save</button>
		</div>
	</div>
</div>

<style>
	.switch {
  		position: relative;
  		display: inline-block;
  		width: 60px;
  		height: 34px;
	}
	.switch input { 
  		opacity: 0;
  		width: 0;
  		height: 0;
	}
	.slider {
  		position: absolute;
  		cursor: pointer;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background-color: #ccc;
		-webkit-transition: .4s;
		transition: .4s;
	}

	.slider:before {
		position: absolute;
		content: "";
		height: 26px;
		width: 26px;
		left: 4px;
		bottom: 4px;
		background-color: white;
		-webkit-transition: .4s;
		transition: .4s;
	}

	input:checked + .slider {
		background-color: #4f46e5;
	}

	input:focus + .slider {
		box-shadow: 0 0 1px #4f46e5;
	}

	input:checked + .slider:before {
		-webkit-transform: translateX(26px);
		-ms-transform: translateX(26px);
		transform: translateX(26px);
	}

	/* Rounded sliders */
	.slider.round {
	border-radius: 34px;
	}

	.slider.round:before {
	border-radius: 50%;
	}
</style>
