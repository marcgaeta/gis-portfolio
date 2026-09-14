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

Created a simple application with an interactive map to quickly lookup parcels and reference GIS data against historical paper maps of coal tracts. Eliminates the manual search and review process comparing a digitial map against local image files, significantly reducing the time needed to confirm tract ownership.

**Study Area:** Schuylkill County  
**Role:** Solo project  
**Status:** Completed

---

## Methods & Tools

**Data Sources**

- Scanned images of historical coal tract paper maps
- Existing County parcel data

**Processing Steps**

1. Created a basemap of parcel, municipal boundary, and coal tract data
2. Imported scanned images to project and manually georeferenced them to align to the basemap parcels
3. Built a user application with a simple interface for searching by parcel location and toggling georeferenced images 
4. Created ArcGIS Online account for a non-technical user and provided training on application access and use

**Tools Used**

| Tool | Purpose |
|------|---------|
| ArcGIS Pro |  Basemap creation and georeferencing |
| ArcGIS Experience Builder | Built simple application interface for non-technical users |

---

## Links

[View Dashboard](https://services.co.schuylkill.pa.us/portal/apps/storymaps/stories/11f1f36834f94ec1a8f1463988e8a089){ .md-button }