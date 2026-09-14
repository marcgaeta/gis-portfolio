---
hide:
  - toc
  - navigation
---


<div class="img-gallery" id="map-gallery-gallery">
  <div class="img-gallery-item"><img src="../assets/images/ped-shed.png" alt="Ped Shed"></div>
  <div class="img-gallery-item"><img src="../assets/images/swmp-access.png" alt="Solid Waste Management Plan"></div>
  <div class="img-gallery-item"><img src="../assets/images/zhb-zoning.png" alt="ZHB Zoning"></div>
  <div class="img-gallery-item"><img src="../assets/images/va-historic.png" alt="Historic Charlottesville"></div>
  <div class="img-gallery-item"><img src="../assets/images/HUC-8.png" alt="Watersheds"></div>
  <div class="img-gallery-item"><img src="../assets/images/lu-analysis.png" alt="Land Use Suitability"></div>
</div>

<div class="img-lightbox" id="map-gallery-lightbox">
  <button class="img-lightbox-close" aria-label="Close">×</button>
  <img src="" alt="Expanded image">
</div>

<script>
(function () {
  const gallery = document.getElementById('map-gallery-gallery');
  const lightbox = document.getElementById('map-gallery-lightbox');
  if (!gallery || !lightbox) return;

  const lightboxImg = lightbox.querySelector('img');
  const closeBtn = lightbox.querySelector('.img-lightbox-close');

  gallery.querySelectorAll('.img-gallery-item img').forEach((img) => {
    img.addEventListener('click', () => {
      lightboxImg.src = img.src;
      lightboxImg.alt = img.alt;
      lightbox.classList.add('is-open');
    });
  });

  function close() {
    lightbox.classList.remove('is-open');
    lightboxImg.src = '';
  }

  closeBtn.addEventListener('click', close);
  lightbox.addEventListener('click', (e) => {
    if (e.target === lightbox) close();
  });
  document.addEventListener('keydown', (e) => {
    if (e.key === 'Escape') close();
  });
})();
</script>