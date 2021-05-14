<template>
  <div class="location container">
    <div class="inner-location">
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
  padding: 1em 0;
}

.headline {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: absolute;
  background: var(--light);
  color: var(--dark);
  width: 16em;
  height: 2em;
  padding: 2em 0;
  transform: rotate(-15deg);
}

.address {
  display: flex;
  flex-direction: column;
  font-family: mono45-headline, monospace;
  font-size: 1.3rem;
  text-transform: uppercase;
  margin: 1em 0 4em 0;
}

.address span:nth-child(3) {
  color: var(--primary);
}

.mapouter {
  position: relative;
  text-align: right;
  padding-bottom: 5em;
}

.gmap {
  display: flex;
  flex-direction: column;
}

#gmap_canvas {
  height: 20em;
}

@media only screen and (min-width: 768px) {
  .info h2 {
    font-size: 3.5rem;
  }

  .headline {
    left: -1em;
    width: 26em;
    padding: 2.7em 0;
  }

  .address {
    font-size: 2rem;
  }
}

@media only screen and (min-width: 1024px) {
  .location {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    height: 100vh;
  }

  .inner-location {
    display: flex;
    flex-direction: column;
    align-self: flex-end;
    justify-content: center;
  }

  .headline img {
    width: 28em;
  }

  .mapouter {
    display: flex;
    flex-direction: column;
    align-self: flex-end;
    justify-content: center;
  }
  #gmap_canvas {
    width: 20em;
    height: 31.7em;
  }
}
</style>