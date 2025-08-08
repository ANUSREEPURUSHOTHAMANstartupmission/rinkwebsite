<script>
  // 59 images (only src for now — you can add titles later)
  const images = [
    { src: '/img/gallery/gallery-059.jpg',title:"RINK Exposure Visit at Institute of Advanced Virology, Thonnakkal" },
    { src: '/img/gallery/gallery-059.jpeg',title:"RINK Exposure Visit at KSCSTE-MBGIPS, Calicut" },
    { src: '/img/gallery/gallery-060.jpeg',title:"RINK Exposure Visit at KSCSTE-MBGIPS, Calicut" },
    { src: '/img/gallery/gallery-017.jpg',title:"RINK Online Demo Day with ICAR- ICAR-Sugarcane Breeding Institute-Research Centre, Kannur" },
    { src: '/img/gallery/gallery-019.jpg',title:"Meet The Expert' Program" },
    { src: '/img/gallery/gallery-028.jpg',title:"RINK Exposure Visit at CIPET: Institute of Petrochemicals Technology (IPT) - Kochi" },
    { src: '/img/gallery/gallery-053.jpg',title:"RINK Exposure Visit at CSIR-NIIST,Thiruvananthapuram" },
    { src: '/img/gallery/gallery-054.jpg',title:"RINK Exposure Visit at ICAR-Sugarcane Breeding Institute-Research Centre, Kannur" },
    { src: '/img/gallery/gallery-045.jpg',title:"MoA signing with MG University for Research Incubation Pprgram" },
    { src: '/img/gallery/gallery-037.jpg',title:"RINK Exposure Visit at ICAR-CTCRI, Sreekaryam" },
    { src: '/img/gallery/gallery-039.jpg',title:"RINK Technology Expo & Conclave 2023" },
    { src: '/img/gallery/gallery-040.jpg',title:"RINK at Kerala Science Congress" },
    { src: '/img/gallery/gallery-043.jpg',title:"RINK Exposure Visit to CLIF, University Of Kerala" }
   
  ];

  let currentPage = 1;
  const perPage = 13;

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
    height: 220px;
    object-fit: cover;
    border-radius: 8px;
  }

  .overlay-wrapper {
    position: relative;
    overflow: hidden;
  }

  .overlay-text {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0, 0, 0, 0.765);
    color: white;
    padding: 8px 12px;
    font-size: 14px;
    text-align: center;
    opacity: 0;
    transition: opacity 0.3s ease;
    border-radius: 0 0 8px 8px;
  }

  .overlay-wrapper:hover .overlay-text {
    opacity: 1;
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
            <div class="gallery-icon overlay-wrapper">
              
                <img src={img.src} alt={img.title ?? 'Gallery Image'} />
                {#if img.title}
                  <div class="overlay-text z-50 text-white">{img.title}</div>
                {/if}
              
            </div>
          </div>
        </div>
      {/each}
    </div>

    <!-- Pagination Controls -->
    <!-- <div class="pagination">
      <button on:click={prevPage} disabled={currentPage === 1}>Previous</button>
      <span class="pt-2">Page {currentPage} of {totalPages}</span>
      <button on:click={nextPage} disabled={currentPage === totalPages}>Next</button>
    </div> -->
  </div>
</div>






 <!-- const images = [
    { src: '/img/gallery/gallery-059.jpg',title:"RINK Exposure Visit at Institute of Advanced Virology, Thonnakkal" },
    { src: '/img/gallery/gallery-059.jpeg',title:"RINK Exposure Visit at KSCSTE-MBGIPS, Calicut" },
    { src: '/img/gallery/gallery-060.jpeg',title:"RINK Exposure Visit at KSCSTE-MBGIPS, Calicut" },
    { src: '/img/gallery/gallery-017.jpg',title:"RINK Online Demo Day with ICAR- ICAR-Sugarcane Breeding Institute-Research Centre, Kannur" },
    { src: '/img/gallery/gallery-019.jpg',title:"Meet The Expert' Program" },
    { src: '/img/gallery/gallery-028.jpg',title:"RINK Exposure Visit at CIPET: Institute of Petrochemicals Technology (IPT) - Kochi" },
    { src: '/img/gallery/gallery-053.jpg',title:"RINK Exposure Visit at CSIR-NIIST,Thiruvananthapuram" },
    { src: '/img/gallery/gallery-054.jpg',title:"RINK Exposure Visit at ICAR-Sugarcane Breeding Institute-Research Centre, Kannur" },
    { src: '/img/gallery/gallery-045.jpg',title:"MoA signing with MG University for Research Incubation Pprgram" },
    { src: '/img/gallery/gallery-037.jpg',title:"RINK Exposure Visit at ICAR-CTCRI, Sreekaryam" },
    { src: '/img/gallery/gallery-039.jpg',title:"RINK Technology Expo & Conclave 2023" },
    { src: '/img/gallery/gallery-040.jpg',title:"RINK at Kerala Science Congress" },
    { src: '/img/gallery/gallery-043.jpg',title:"RINK Exposure Visit to CLIF, University Of Kerala" },
    { src: '/img/gallery/gallery-001.jpg' },
    { src: '/img/gallery/gallery-002.jpg' },
    { src: '/img/gallery/gallery-003.jpg' },
    { src: '/img/gallery/gallery-004.jpg' },
    { src: '/img/gallery/gallery-005.jpg' },
    { src: '/img/gallery/gallery-006.jpg' },
    { src: '/img/gallery/gallery-007.jpg' },
    { src: '/img/gallery/gallery-008.jpg' },
    { src: '/img/gallery/gallery-009.jpg' },
    { src: '/img/gallery/gallery-010.jpg' },
    { src: '/img/gallery/gallery-011.jpg' },
    { src: '/img/gallery/gallery-012.jpg' },
    { src: '/img/gallery/gallery-013.jpg' },
    { src: '/img/gallery/gallery-014.jpg' },
    { src: '/img/gallery/gallery-015.jpg' },
    { src: '/img/gallery/gallery-016.jpg' },
    { src: '/img/gallery/gallery-018.jpg' },
    { src: '/img/gallery/gallery-020.jpg' },
    { src: '/img/gallery/gallery-021.jpg' },
    { src: '/img/gallery/gallery-022.jpg' },
    { src: '/img/gallery/gallery-023.jpg' },
    { src: '/img/gallery/gallery-024.jpg' },
    { src: '/img/gallery/gallery-025.jpg' },
    { src: '/img/gallery/gallery-026.jpg' },
    { src: '/img/gallery/gallery-027.jpg' },
    { src: '/img/gallery/gallery-029.jpg' },
    { src: '/img/gallery/gallery-030.jpg' },
    { src: '/img/gallery/gallery-031.jpg' },
    { src: '/img/gallery/gallery-032.jpg' },
    { src: '/img/gallery/gallery-033.jpg' },
    { src: '/img/gallery/gallery-034.jpg' },
    { src: '/img/gallery/gallery-035.jpg' },
    { src: '/img/gallery/gallery-036.jpg' },
    { src: '/img/gallery/gallery-038.jpg' },
    { src: '/img/gallery/gallery-041.jpg' },
    { src: '/img/gallery/gallery-042.jpg' },
    { src: '/img/gallery/gallery-044.jpg' },
    { src: '/img/gallery/gallery-046.jpg' },
    { src: '/img/gallery/gallery-047.jpg' },
    { src: '/img/gallery/gallery-048.jpg' },
    { src: '/img/gallery/gallery-049.jpg' },
    { src: '/img/gallery/gallery-050.jpg' },
    { src: '/img/gallery/gallery-051.jpg' },
    { src: '/img/gallery/gallery-052.jpg' },
    { src: '/img/gallery/gallery-055.jpg' },
    { src: '/img/gallery/gallery-056.jpg' },
    { src: '/img/gallery/gallery-057.jpg' },
    { src: '/img/gallery/gallery-058.jpg' },
   
  ]; -->