<template>
  <div class="location">
    <div class="info">
      <div class="headline">
        <h2>Where to find us</h2>
      </div>
      <img src="../../public/img/takeaway.jpg" alt="" />
    </div>

    <div class="address">
      <span>Travessa harmônia, 45</span>
      <span>Florianópolis, Santa Catarina</span>
      <span>+55 48 3879-7503</span>
    </div>

    <div class="mapouter">
      <div class="gmap">
        <iframe
          id="gmap_canvas"
          src="https://maps.google.com/maps?q=Travessa%20harm%C3%B4nia,%2045%20Florian%C3%B3polis,%20Santa%20Catarina&t=&z=13&ie=UTF8&iwloc=&output=embed"
          frameborder="0"
          scrolling="no"
          marginheight="0"
          marginwidth="0"
        ></iframe>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Location",
};
</script>

<style scoped>
.info {
  position: relative;
}

.info h2 {
  font-size: 2rem;
  text-transform: uppercase;
}

.info img {
  padding: 1em;
}

.headline {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: absolute;
  background: var(--light);
  color: var(--dark);
  width: 21em;
  height: 2em;
  padding: 2em 0;
  transform: rotate(-15deg);
}

.address {
  display: flex;
  flex-direction: column;
  font-size: 1.5rem;
  text-transform: uppercase;
  margin: 1em 0.8em 4em 0.8em;
}

.address span:nth-child(3) {
  color: var(--primary);
}

.mapouter {
  position: relative;
  text-align: right;
  padding: 0 1em 5em 1em;
}

.gmap {
  display: flex;
  flex-direction: column;
}

#gmap_canvas {
  height: 20em;
}
</style>