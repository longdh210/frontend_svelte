<script>
	import NavBar from "../../components/NavBar/NavBar.svelte";
	import edit from "../../assets/edit.png";
	import settings from "../../assets/settings.png";
	import avt from "../../assets/avt.png";
	import paper from "../../assets/paper-plane.png";
	import add from "../../assets/add2.png";
	import moon from "../../assets/new-moon.png";
	import add2 from "../../assets/add (2).png";
	import moment from "../../assets/profile-page-image.jpeg";
	import bg from "../../assets/profile-page-bg.jpeg";
	import plus from "../../assets/plus.png";

	let current = 'global';
</script>

<div class="w-screen h-screen bg-slate-200 flex flex-col md:flex-row">
	<NavBar></NavBar>
	<div class="h-full sm:w-full sm:h-full md:w-[80%] md:h-full lg:w-[60%] lg:h-full bg-white flex-none flex-col overflow-y-scroll overflow-x-hidden border-0">
		<div class="h-[8%] w-full flex flex-row justify-end mt-5">
			<img class="h-[50%] mr-4" src={edit} alt="edit"/>
			<img class="h-[50%] mr-4" src={settings} alt="edit"/>
		</div>
		<div class="flex flex-row w-full">
			<div class="flex items-center flex-col justify-center">
				<div>
					<h1 class="font-bold text-3xl">Melon62</h1>
				</div>
				<div class="ml-3">
					<span class="font-bold">0</span>
					<span>followers</span>
					<span class="font-bold ml-2">0</span>
					<span>followers</span>
				</div>
			</div>
			<div class="relative flex justify-end w-[70%]">
				<div class="w-20 h-20 bg-slate-100 border rounded-[50px] absolute -right-12 flex justify-center items-center">
					<img class="w-5" src={plus} alt="plus"/>
				</div>
				<img class="w-20 h-20 bg-sky-100 border rounded-[50px] absolute" src={avt} alt="alt"/>
			</div>
		</div>
		<div class="h-[5%] w-full flex justify-center mt-10">
			<div class="h-[100%] w-[90%] bg-slate-200 border rounded-2xl flex flex-row justify-center items-center">
				<img class="h-[50%] mr-2" src={paper} alt="paper"/>
				<span>Message</span>
			</div>
		</div>
		<div class="h-[5%] w-full flex justify-center mt-5">
			<div class="h-[100%] w-[90%] bg-slate-100 border-dashed border-2 rounded-3xl flex flex-row justify-center items-center">
				<img class="h-[60%] mr-2" src={add} alt="add"/>
				<span>Shall we make the profile even cooler?</span>
			</div>
		</div>
		<div class="h-[8%] w-full flex justify-center mt-2">
			<span>You can make various introductions such as ID, notice and more.</span>
		</div>
		<div class="mb-3 w-full">
			<div class="flex justify-center border-b-2" >
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<span class="inline-block font-bold text-xl mr-5 {current === 'global' ? 'selected' : ''}" on:click={() => current = 'global'} >	
					Moment
				</span>
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<span class="inline-block font-bold text-xl {current === 'my' ? 'selected' : ''}" on:click={() => current = 'my'}>
					Talk
				</span>
			</div>
			<div class="w-full mt-5">
				{#if current === "global"}
					<div class= "flex justify-center mb-5">
						<div class="h-28 w-[80%] border-2 border-dashed rounded-xl flex flex-row overflow-hidden">
							<div class="relative w-[30%]">
								<img class="w-[40%] absolute top-[15%] right-[10%]" src={moon} alt="moon"/>
								<img class="w-[15%] absolute top-[20%] right-[40%]"src={add} alt="alt"/>
							</div>
							<div class="flex flex-col w-[70%] justify-center overflow-auto">
								<span>Make Moment</span>
								<span>You can notify Meet-Ups of different themes</span>
							</div>
						</div>
					</div>
					<div>
						<span class="text-xl ml-3">Participated Moment</span>
						<div class="flex flex-row justify-center items-center mt-5">
							<img class='w-[5%] h-[5%] mr-8' src={add2} alt="add2"/>
							<img class="w-[15%] mr-3" src={moment} alt="moment"/>
							<img class="w-[15%] mr-3" src={moment} alt="moment"/>
							<img class="w-[15%]" src={moment} alt="moment"/>
						</div>
					</div>
				{:else if current === "my"}
				<div class= "flex justify-center mb-5">
					<div class="h-28 w-[80%] border-2 border-dashed rounded-xl flex flex-row overflow-hidden">
						<div class="relative w-[30%]">
							<img class="w-[40%] absolute top-[15%] right-[10%]" src={moon} alt="moon"/>
							<img class="w-[15%] absolute top-[20%] right-[40%]"src={add} alt="alt"/>
						</div>
						<div class="flex flex-col w-[70%] justify-center overflow-auto">
							<span>Write a Message</span>
							<span>A photo is fine, too! Feel free to talk about anything.</span>
						</div>
					</div>
				</div>
				{/if}
			</div>
		</div>
	</div>
</div>

<style>
	.selected {
		color: #8776ef;
		border-bottom: 3px solid #8776ef;
	}
</style>
