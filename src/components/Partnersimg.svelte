<script>
  // Number of images in your gallery
  const totalImages = 23; // change as needed
  const images = Array.from({ length: totalImages }, (_, i) => {
    const num = String(i + 1).padStart(3, '0'); // 001, 002, ...
    return `/img/logo/logo-${num}.jpg`; // adjust path as needed
  });
</script>

<div class="grid md:grid-cols-6 sm:grid-cols-3 grid-cols-3 gap-10 h-auto">
    {#each images as img}
        <div >
            <div class="border p-3">
               <img src={img} alt="Gallery image" class="">
            </div>
        </div>
    {/each}
</div>
