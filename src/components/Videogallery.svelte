<script>
   
    import programs from './data/video.json';

    let popup_open=false;
    let target_val='';
    let currentIndex = 0;

    function hotel_popup(e){
        target_val = e.currentTarget.getAttribute("data-target");
        if(target_val){
            popup_open=true;
        }
    }

    function close_popup(){
        popup_open=false;
    }

    
</script>

<div class="">
  
<div class="md:grid-cols-3 sm:grid-cols-2 grid-cols-1 grid gap-4 h-auto">
    {#each programs as program}
        <div class="video-item relative">
            <!-- Thumbnail with Play Icon Overlay -->
            <div class="rs-videos orange-videos relative cursor-pointer" data-target="{program.youtube_id}" on:click={hotel_popup}>
                <img src={`https://img.youtube.com/vi/${program.youtube_id}/maxresdefault.jpg`} 
                     alt={program.label} 
                     class="rounded-md w-full">
                <div class=" absolute inset-0 flex items-center justify-center">
                    <a class=" bg-blue-600 rounded-full p-6 w-10 h-10 flex flex-col items-center justify-center popup-videos animate-pulse" 
                       href={`https://www.youtube.com/watch?v=${program.youtube_id}`}>
                        <i class="fa fa-play text-white text-xl"></i>
                    </a>
                </div>
            </div>

            <!-- Program Label -->
            <div class="mt-3 text-center">
                {#if program.label}
                    {program.label}
                {/if}
            </div>
        </div>
    {/each}
</div>

     
  
</div>
