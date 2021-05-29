<template>
  <div>
    <router-link class="link" :to="{ path: '/menu', hash: '#section-menu' }">
      <a href="" class="btn">Order Now</a>
    </router-link>
    <router-view />
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
a.btn {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 13em;
  height: 4.5em;
  font-size: 0.8rem;
  text-decoration: none;
  color: var(--primary);
  background: transparent;
  text-transform: initial;
  border: 2px solid var(--dark);
}

a.btn:hover {
  background: var(--primary);
  border: none;
  color: var(--light);
}
</style>