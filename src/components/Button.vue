<template>
  <div>
    <a href="" class="btn">Order Now</a>
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
  border: 1px solid var(--dark);
  margin-top: -10em;
}

a.btn:hover {
  background: var(--primary);
  border: none;
  color: var(--light);
}
</style>