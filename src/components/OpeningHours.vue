<template>
  <div class="opening-hours" id="section-openinghours">
    <h2>Opening Hours</h2>
    <h4>Tuesday - Sunday</h4>
    <h4>19:00 - 23:30</h4>
  </div>
</template>

<script>
export default {
  name: "OpeningHours",
};
</script>

<style scoped>
.opening-hours {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  height: 30em;
}

h2 {
  padding: 0.5em;
  color: var(--primary);
  text-transform: uppercase;
  font-size: 2rem;
}

h4 {
  padding: 0.2em;
}

@media only screen and (min-width: 768px) {
  .opening-hours {
    font-size: 1.8rem;
    height: 23em;
  }

  h2 {
    font-size: 4rem;
  }
}
</style>