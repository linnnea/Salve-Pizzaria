<template>
  <nav>
    <div class="left">left</div>
    <div class="logo">Salve! Pizzaria</div>
    <div class="menu">Menu</div>
  </nav>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  text-transform: uppercase;
  border-bottom: 1px solid black;
}

nav > * {
  padding: 1.5em 1em;
}

.menu {
  background: var(--dark);
  color: var(--light);
}
</style>