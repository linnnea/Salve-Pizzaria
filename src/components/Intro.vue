<template>
  <div>
    <div class="salve-3x">
      <span>Salve</span>
      <span>Salve</span>
      <span
        >Salve
        <span class="small">
          is a friendly way of saying hi. It represents the passion and
          friendliness of Neapolitan people.
        </span></span
      >

      <div class="intro-img">
        <img src="../../public/img/intro.png" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Intro",
};
</script>

<style scoped>
.salve-3x {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: relative;
  height: 25em;
  padding: 2em;
}

.salve-3x span {
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
  -webkit-text-stroke: 1px black;
  color: transparent;
}
.salve-3x span:nth-child(3) {
  padding-top: 0.25em;
  line-height: 0.7;
  color: var(--primary);
}

span.small {
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
</style>