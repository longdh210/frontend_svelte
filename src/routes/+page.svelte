<script>
	import logo from "../assets/logo.webp";
	import person from "../assets/person.png"
	import tid from "../assets/tidIcon.png";
	import kakao from "../assets/kakaoIcon.png";
	import fb from "../assets/fbIcon.png";
	import gg from "../assets/ggIcon.png";
	import "../app.css";
	import { goto } from '$app/navigation';
	import SignInButton from "../components/Buttons/signIn.svelte";
	function navigate() {
		goto("/home")
	}
</script>

<!-- <svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head> -->

<main>
	<div class="w-screen h-screen bg-sky-300 flex justify-center items-center">
		<div class="sm:w-full sm:h-full lg:w-2/5 lg:h-3/4 bg-white flex flex-col items-center border rounded-lg">
			<div class="mt-10">
				<h1 class="font-title font-bold text-fuchsia-500 text-6xl">ifland</h1>
			</div>
			<div>
				<h2 class="mt-5">User login is required</h2>
			</div>
			<div class="w-1/4 mt-5">
				<img src={person} alt="person"/>
			</div>
			<div class="mt-10 lg:mt-2">
				<SignInButton icon={tid} title="Sign in with T ID"></SignInButton>
				<SignInButton icon={kakao} title="Sign in with Kakao"></SignInButton>
				<SignInButton icon={fb} title="Sign in with Facebook"></SignInButton>
				<SignInButton icon={gg} title="Sign in with Google"></SignInButton>
			</div>
		</div>
	</div>
</main>

<style>
</style>
