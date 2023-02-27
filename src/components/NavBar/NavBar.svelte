<script>
    import home from "../../assets/home.png";
	import star from "../../assets/star.png";
	import vest from "../../assets/vest.png";
	import user from "../../assets/user.png";
	import menu from "../../assets/menu.png";
	import add from "../../assets/add.png";
	import { onMount } from "svelte";

  let menuBar = false;
  let status = "/home";
  onMount(async () => {
    console.log(window.location.pathname);
    status = window.location.pathname;
  })
</script>

<div class="w-full h-full flex justify-end text-end mr-2 sm:w-full mt-2">
    <nav class="h-[10%]">
        <div class="w-full cursor-pointer md:hidden flex justify-end px-4 border-r-4 border-slate-100 mb-2 mt-2">
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <img class="w-[5%] sm:w-[3%]" src={menu} alt="menu" 
            on:click={() => menuBar = !menuBar}/>
        </div>
      <ul class="{menuBar == true ? "" : "hidden"} md:block">
        <li class="mb-2">
          <a class="px-4 border-r-4 {status === '/home' ? 'selected' : 'noselect'} flex items-center justify-end" href="/home"
          >
            <span>Home</span>
            <img class="w-[3%] md:w-[15%] lg:w-[5%] xl:w-[3%] inline-block ml-2" src={home} alt="home"/>
          </a>
        </li>
        <li class="mb-2">
          <a class="px-4 border-r-4 {status === '/about' ? 'selected' : 'noselect'} flex items-center justify-end" href="/about"
          >
            <span>About</span>
            <img class="w-[3%] md:w-[15%] lg:w-[5%] xl:w-[3%] inline-block ml-2" src={star} alt="About"/>
          </a>
        </li>
        <li class="mb-2">
            <a class="px-4 border-r-4 {status === '/add' ? 'selected' : 'noselect'} flex items-center justify-end" href="/add"
            >
              <span>Add</span>
              <img class="w-[3%] md:w-[15%] lg:w-[5%] xl:w-[3%] inline-block ml-2" src={add} alt="Add"/>
            </a>
        </li>
        <li class="mb-2">
          <a class="px-4 border-r-4 {status === '/character' ? 'selected' : 'noselect'} flex items-center justify-end" href="/character"
          >
            <span>Character</span>
            <img class="w-[3%] md:w-[15%] lg:w-[5%] xl:w-[3%] inline-block ml-2" src={vest} alt="vest"/>
          </a>
        </li>
        <li class="mb-2">
            <a class="px-4 border-r-4 {status === '/profile' ? 'selected' : 'noselect'} flex items-center justify-end" href="/profile"
            >
              <span>Profile</span>
              <img class="w-[3%] md:w-[15%] lg:w-[5%] xl:w-[3%] inline-block ml-2" src={user} alt="user"/>
            </a>
          </li>
      </ul>
    </nav>
</div>

<style>
  .selected {
		border-color: #f59e0b;
	}
  .noselect {
    border-color: #f1f5f9;
  }
</style>