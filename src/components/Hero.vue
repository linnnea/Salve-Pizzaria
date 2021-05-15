<template>
  <div class="hero">
    <h1>S</h1>

    <Button />
  </div>
</template>

<script>
import Button from "./Button.vue";

export default {
  name: "Hero",
  components: {
    Button,
  },
};
</script>

<style scoped>
.hero {
  display: grid;
  place-items: center;
  height: 100vh;
  font-size: 13rem;
  text-transform: uppercase;
}

h1 {
  font-family: anton, sans-serif;
  color: var(--primary);
}
</style>