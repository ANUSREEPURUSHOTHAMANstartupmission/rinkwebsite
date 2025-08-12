<script>
   
    import programs from './data/startups.json';

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
  
<div class="md:grid-cols-4 lg:grid-cols-6 sm:grid-cols-2 grid-cols-2 grid gap-4 h-auto">
    {#each programs as program}
        <div class="">
            <div class=" bg-white">
                <img src="{program.img}" class="md:p-8 p-2 border"> 
            </div>

            <div class="mt-3 text-center md:text-base text-sm">
                {#if program.label}
                    {program.label}
                {/if}
            </div>
        </div>
    {/each}
</div>

     
  
</div>
