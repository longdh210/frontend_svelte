<script>
	import '../../app.css';
    /**
	 * @type {any}
	 */
     export let icon;
    /**
	 * @type {any}
	 */
     export let title;
     /**
	 * @type {any}
	 */
      export let onClick;
</script>

<div class="w-72 mt-5">
    <button class="h-8 border border-slate-300 rounded-lg hover:bg-gray-200" on:click={onClick}>
        <img class="w-1/12 inline float-left ml-1" src={icon} alt="tid"/>
        {title}
    </button>
</div>

