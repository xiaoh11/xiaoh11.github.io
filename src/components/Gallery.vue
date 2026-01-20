<template>
  <section class="gallery">
    <div class="gallery-grid">
      <!-- <div class="gallery-item" style="background-image: url('/Figure/IMG_1667 2.JPG')"></div>
      <div class="gallery-item" style="background-image: url('/Figure/IMG_1668.JPG')"></div> -->
      <div class="gallery-item" style="background-image: url('/Figure/IMG_9058.jpg')"></div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Gallery'
}
</script>

<style scoped>
.gallery {
  background: var(--bg-primary);
  padding: 0;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 0;
}

.gallery-item {
  height: 400px;
  background-size: cover;
  background-position: center;
  transition: var(--transition);
  cursor: pointer;
}

.gallery-item:hover {
  transform: scale(1.05);
  z-index: 10;
}
</style>
