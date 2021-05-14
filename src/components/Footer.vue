<template>
  <footer>
    <span>© IMAGES - FATFACESTUDIO</span>
    <span>© SITE DESIGN - LINNÉA WENNBERG</span>
    <span>ALL RIGHTS RESERVED</span>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
footer {
  display: flex;
  flex-direction: column;
  text-align: center;
  background: var(--primary);
  color: var(--dark);
  padding: 2em 1em;
  font-size: 0.9rem;
}

@media only screen and (min-width: 768px) {
  footer {
    flex-direction: row;
    justify-content: space-evenly;
    padding: 1em;
  }
}
</style>