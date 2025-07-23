<script>
  import { onMount } from 'svelte';

  // Total number of images (update as needed)
  const totalImages = 35;
  const images = Array.from({ length: totalImages }, (_, i) => {
    const num = String(i + 1).padStart(3, '0'); // gallery-001.jpg
    return `/img/gallery/gallery-${num}.jpg`;
  });

  // Pagination
  let currentPage = 1;
  const perPage = 12;

  $: totalPages = Math.ceil(images.length / perPage);
  $: paginatedImages = images.slice((currentPage - 1) * perPage, currentPage * perPage);

  function nextPage() {
    if (currentPage < totalPages) currentPage++;
  }

  function prevPage() {
    if (currentPage > 1) currentPage--;
  }
</script>

<style>
  .gallery-icon img {
    width: 100%;
    height: 220px; /* Fixed height */
    object-fit: cover; /* Crop proportionally */
    border-radius: 8px;
  }
  .pagination {
    display: flex;
    justify-content: center;
    gap: 2rem;
    margin-top: 20px;
  }
  .pagination button {
    padding: 8px 16px;
    background: #071478;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  .pagination button:disabled {
    background: #ccc;
    cursor: not-allowed;
  }
</style>

<div class="rs-gallery gallery-style1 pb-24 pt-10">
  <div class="container">
    <div class="row">
      {#each paginatedImages as img}
        <div class="col-lg-3 col-md-6 mb-30">
          <div class="gallery-item">
            <div class="gallery-icon">
              <a class="image-popup" href={img}><img src={img} alt="Gallery Image" /></a>
            </div>
          </div>
        </div>
      {/each}
    </div>

    <!-- Pagination Controls -->
    <div class="pagination">
      <button class="w-24" on:click={prevPage} disabled={currentPage === 1}>Previous</button>
      <span class="pt-2">Page {currentPage} of {totalPages}</span>
      <button class="w-24" on:click={nextPage} disabled={currentPage === totalPages}>Next</button>
    </div>
  </div>
</div>
