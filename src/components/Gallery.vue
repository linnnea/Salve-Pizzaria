<template>
  <div class="gallery container">
    <div class="gallery-img border">
      <img src="../../public/img/inside.jpg" alt="" />
    </div>
    <div class="gallery-img border">
      <img src="../../public/img/posters.jpg" alt="" />
    </div>
    <div class="gallery-img border">
      <img src="../../public/img/Cartazes_SALVE.jpeg" alt="" />
    </div>
    <div class="gallery-img">
      <img src="../../public/img/pizza.jpeg" alt="" />
    </div>
    <div class="gallery-img border">
      <img src="../../public/img/lightsign.jpg" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: "Gallery",
};
</script>

<style scoped>
.gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-top: 10em;
}

.gallery-img {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 15em;
  height: auto;
  object-fit: contain;
  margin: 0.5em 0;
}

.gallery-img.border img {
  border: 0.5em solid var(--light);
}

.gallery-img:nth-child(even) {
  transform: rotate(15deg);
}

.gallery-img:nth-child(odd) {
  transform: rotate(-15deg);
}

@media only screen and (min-width: 768px) {
  .gallery-img {
    width: 14em;
  }
}
</style>
