<script>
	import NavBar from "../../components/NavBar/NavBar.svelte";
	import edit from "../../assets/edit.png";
	import settings from "../../assets/settings.png";
	import avt from "../../assets/avt.png";

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
	<div class="h-full sm:w-full sm:h-full md:w-[80%] md:h-full lg:w-[60%] lg:h-full bg-slate-200 flex-none flex-col overflow-y-scroll overflow-x-hidden border-0">
		<div class="h-[10%] w-full flex flex-row justify-end mt-5">
			<img class="h-[40%] mr-4" src={edit} alt="edit"/>
			<img class="h-[40%] mr-4" src={settings} alt="edit"/>
		</div>
		<div class="flex flex-row w-full">
			<div class="flex items-center">
				<div>
					<h1 class="block">Melon62</h1>
				</div>
				<div class="block">
					<span>0</span>
					<span>followers</span>
					<span>0</span>
					<span>followers</span>
				</div>
			</div>
			<div class="flex justify-end w-[70%]">
				<img class="w-[15%] bg-sky-100 border rounded-[50px]" src={avt} alt="alt"/>
			</div>
		</div>
	</div>
</div>

<style>
</style>
