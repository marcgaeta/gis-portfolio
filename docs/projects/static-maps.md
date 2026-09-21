# Site Suitability Analysis

<div class="pdf-slideshow" id="zoning-tracker-slideshow">
  <div class="pdf-slideshow-track">
    <div class="pdf-slideshow-slide is-active"><img src="../../assets/images/inundation-cover.png" alt="Slide 1"></div>
    <div class="pdf-slideshow-slide"><img src="../../assets/images/inundation-a1.png" alt="Slide 2"></div>
    <div class="pdf-slideshow-slide"><img src="../../assets/images/inundation-b1.png" alt="Slide 3"></div>
  </div>
  <button class="pdf-slideshow-arrow pdf-slideshow-arrow--prev" aria-label="Previous slide">‹</button>
  <button class="pdf-slideshow-arrow pdf-slideshow-arrow--next" aria-label="Next slide">›</button>
  <div class="pdf-slideshow-dots"></div>
</div>

<script>
(function () {
  const root = document.getElementById('zoning-tracker-slideshow');
  if (!root) return;
  const slides = root.querySelectorAll('.pdf-slideshow-slide');
  const dotsContainer = root.querySelector('.pdf-slideshow-dots');
  let current = 0;

  slides.forEach((_, i) => {
    const dot = document.createElement('button');
    dot.className = 'pdf-slideshow-dot' + (i === 0 ? ' is-active' : '');
    dot.setAttribute('aria-label', 'Go to slide ' + (i + 1));
    dot.addEventListener('click', () => goTo(i));
    dotsContainer.appendChild(dot);
  });
  const dots = root.querySelectorAll('.pdf-slideshow-dot');

  function goTo(index) {
    slides[current].classList.remove('is-active');
    dots[current].classList.remove('is-active');
    current = (index + slides.length) % slides.length;
    slides[current].classList.add('is-active');
    dots[current].classList.add('is-active');
  }

  root.querySelector('.pdf-slideshow-arrow--prev').addEventListener('click', () => goTo(current - 1));
  root.querySelector('.pdf-slideshow-arrow--next').addEventListener('click', () => goTo(current + 1));
})();
</script>

## Overview

Designed and produced a multi-page, high-resolution technical map series of dam inundation areas for an update to the Schuylkill County, Pennsylvania Emergency Action Plan (EAP). The map series delineates modeled flood inundation boundaries across a gridded tile map to support emergency responders and local planning authorities in flood risk visualization and evacuation management.

**Skill Highlight:** Techincal map and document creation

**Study Area:** Schuylkill County  
**Role:** Contributor 
**Status:** Completed

---

## Methods & Tools

**Processing Steps**

1. Configured dynamic grid-based Map Series in ArcGIS Pro to generate a standardized, multi-sheet atlas at a 1:12,000 scale with seamless index key navigation
2. Digitized and symbolized key public safety assets across inundation zones, including designated traffic control points, fire stations, schools, and SARA hazard facilities
3. Integrated hydraulic flood boundary vectors onto high-resolution aerial orthophotography to show affected parcels, roadways, and buildings
4. Consulted with project engineers to review hydraulic flood model outputs and refined inundation boundaries, map extents, and critical asset overlays across multiple design iterations to ensure accurate hazard representation
5. Repeated process for all 5 county dams and wrote up workflow

**Tools Used**

| Tool | Purpose |
|------|---------|
| ArcGIS Pro |  Map series and layout creation |
| Word & PDF Processor |  Technical documentation |

---