<script>
	import '../../app.css';
    import tid from '../../assets/tidIcon.png';
    /**
	 * @type {any}
	 */
     export let icon;
    /**
	 * @type {any}
	 */
     export let title;
</script>

<div class="w-72 mt-5">
    <button class="h-8 border border-slate-300 rounded-lg hover:bg-gray-200">
        <img class="w-1/12 inline float-left ml-1" src={icon} alt="tid"/>
        {title}
    </button>
</div>

