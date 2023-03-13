<script>
    import cross from "../../assets/cross.png";
    import NoticeForm from "../../components/Informaton/NoticeForm.svelte";
</script>

<div class="w-screen h-screen sm:bg-sky-300 flex justify-center items-center">
    <div class="w-full h-full sm:w-full sm:h-full lg:w-2/5 lg:h-3/4 bg-white flex flex-col items-start border rounded-lg">
        <div class="w-full flex justify-end p-2">
            <img class="w-5" src={cross} alt="cross" />
        </div>
        <div class="mt-2 ml-3 mb-5">
            <h1 class="font-bold text-2xl">Notice</h1>
        </div>
        <div class="w-full border-0 border-b-2 mb-5">
        </div>
        <div class="w-full">
            <NoticeForm></NoticeForm>
            <NoticeForm></NoticeForm>
            <NoticeForm></NoticeForm>
            <NoticeForm></NoticeForm>
        </div>
        <div class="w-full flex justify-center">
            <button class="border-2 rounded-[25px] p-2 border-slate-400">See more</button>
        </div>
    </div>
</div>