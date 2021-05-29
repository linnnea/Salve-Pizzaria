<template>
  <div class="hero" id="home">
    <div class="marquee">
      <div class="track">
        <div class="content">
          SALVE! PIZZARIA 
          SALVE! PIZZARIA 
          SALVE! PIZZARIA 
          SALVE! PIZZARIA 
          SALVE! PIZZARIA
        </div>
      </div>
    </div>
    <Button />
  </div>
</template>

<script>
import Button from "../components/Button";

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
  text-transform: uppercase;
}

.marquee {
  display: flex;
  align-items: flex-end;

  position: relative;
  width: 100vw;
  max-width: 100%;
  height: 30em;
  overflow-x: hidden;
}

.track {
  position: absolute;
  white-space: nowrap;
  will-change: transform;
  animation: marquee 32s linear infinite;
}

.content {
  padding-top: .05em;
  font-family: anton, sans-serif;
  font-size: 21rem;
  line-height: 1;
  color: var(--primary);
}

@keyframes marquee {
  from { transform: translateX(0); }
  to { transform: translateX(-50%); }
}


</style>