<template>
  <div class="salve-3x container" id="section-intro">
    <span>Salve</span>
    <span>Salve</span>
    <span>Salve
      <span class="small">
        is a friendly way of saying hi. It represents the passion and
        friendliness of Neapolitan people.
      </span></span>
    <div class="intro-img">
      <img src="../assets/intro.png" alt="" />
    </div>
  </div>
</template>

<style scoped>
.salve-3x {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: relative;
  height: 25em;
}

.salve-3x span {
  font-family: anton, sans-serif;
  font-size: 3rem;
  text-transform: uppercase;
}

.salve-3x p {
  font-size: initial;
}

.salve-3x span:nth-child(1) {
  color: var(--primary);
}

.salve-3x span:nth-child(2) {
  -webkit-text-stroke: 1.2px black;
  color: transparent;
}

.salve-3x span:nth-child(3) {
  padding-top: 0.45em;
  line-height: 0.6;
  color: var(--primary);
}

span.small {
  font-family: droid-sans-mono, monospace;
  font-size: 1.2rem !important;
  color: black !important;
  text-transform: initial;
}

.intro-img {
  position: absolute;
  top: 2em;
  right: 2em;
  -webkit-transform: scaleX(-1);
  transform: scaleX(-1);
}

@media only screen and (min-width: 768px) {
  .salve-3x {
    justify-content: flex-end;
    height: 33em;
    margin-bottom: 10em;
    padding-top: 0;
  }

  .salve-3x span {
    padding-top: 1em;
    font-size: 6rem;
    line-height: 0.2;
  }

  .salve-3x span:nth-child(3) {
    padding-top: 0.8em;
  }

  .intro-img {
    position: absolute;
    bottom: 8em;
    right: 7em;
  }

  .intro-img img {
    width: 18em;
  }
}
</style>