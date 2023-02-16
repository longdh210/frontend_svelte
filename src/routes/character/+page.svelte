<script>
	import "../../app.css";
    import person from "../../assets/person.png";
    import CarouselTest from "../../components/Carousel/CarouselTest.svelte";
    import home from "../../assets/home.png";
	import star from "../../assets/star.png";
	import vest from "../../assets/vest.png";
	import user from "../../assets/user.png";
	import menu from "../../assets/menu.png";

    let images = [
		{title: 'London', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'HCM city', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Da Nang', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Can Tho', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Ca Mau', src: 'https://picsum.photos/800/600?random=2'},
		{title: 'Rach Gia', src: 'https://picsum.photos/800/600?random=2'},
	]
    let menuBar = false;

    function handleOnlickCarousel() {
        console.log("log")
    }
</script>

<div class="w-screen h-screen bg-slate-100 flex flex-col md:flex-row">
    <div class="w-full h-full flex justify-end text-end mr-2 sm:w-full">
		<nav class="h-[10%]">
			<div class="w-full cursor-pointer lg:hidden flex justify-end px-4 border-r-4 border-slate-100 mb-2 mt-2">
				<!-- svelte-ignore a11y-click-events-have-key-events -->
				<img class="w-[5%] sm:w-[3%]" src={menu} alt="menu" on:click={() => menuBar = !menuBar}/>
			</div>
		  <ul class="{menuBar == true ? "" : "hidden"} md:block">
			<li class="mb-2">
			  <a class="px-4 border-r-4 border-amber-500" href="/">
				<span>Home</span>
				<img class="w-[3%] lg:w-[3%] inline-block" src={home} alt="home"/>
			  </a>
			</li>
			<li class="mb-2">
			  <a class="px-4 border-r-4 border-slate-100" href="/about">
				<span>About</span>
				<img class="w-[3%] lg:w-[3%] inline-block" src={star} alt="star"/>
			  </a>
			</li>
			<li class="mb-2">
			  <a class="px-4 border-r-4 border-slate-100" href="/character">
				<span>Character</span>
				<img class="w-[3%] lg:w-[3%] inline-block" src={vest} alt="vest"/>
			  </a>
			</li>
			<li class="mb-2">
				<a class="px-4 border-r-4 border-slate-100" href="/profile">
				  <span>Profile</span>
				  <img class="w-[3%] lg:w-[3%] inline-block" src={user} alt="user"/>
				</a>
			  </li>
		  </ul>
		</nav>
	</div>
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
            <button class="w-[80%] h-[40%] mt-2 border border-slate-400 rounded-lg hover:bg-gray-200 bg-violet-500 text-white">
                Start ifland
            </button>
        </div>
	</div>
</div>
