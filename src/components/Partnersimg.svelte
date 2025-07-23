<script>
  // Number of images in your gallery
  const totalImages = 17; // change as needed
  const images = Array.from({ length: totalImages }, (_, i) => {
    const num = String(i + 1).padStart(3, '0'); // 001, 002, ...
    return `/img/logo/logo-${num}.jpg`; // adjust path as needed
  });
</script>

<div class="grid md:grid-cols-7 sm:grid-cols-3 grid-cols-2 gap-10 h-auto">
    {#each images as img}
        <div >
            <div>
               <img src={img} alt="Gallery image" class="">
            </div>
        </div>
    {/each}
</div>
