<template>
  <div class="container-menu container">
    <div class="menu">
      <div class="menu-inner">
        <h1>Menu</h1>
        <div class="menu-inner-text">
          <div class="pizza">
            <div class="pizza-name">Margherita</div>
            <div class="pizza-price">14$</div>
          </div>
          <div class="pizza">
            <div class="pizza-name">Margherita</div>
            <div class="pizza-price">14$</div>
          </div>
          <div class="pizza">
            <div class="pizza-name">Margherita</div>
            <div class="pizza-price">14$</div>
          </div>
          <div class="pizza">
            <div class="pizza-name">Margherita</div>
            <div class="pizza-price">14$</div>
          </div>
          <div class="pizza">
            <div class="pizza-name">Margherita</div>
            <div class="pizza-price">14$</div>
          </div>
          <div class="pizza">
            <div class="pizza-name">Margherita</div>
            <div class="pizza-price">14$</div>
          </div>
        </div>
      </div>
    </div>
    <div class="menu-img">
      <img src="../assets/menu.jpg" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: "Menu",
};
</script>

<style scoped>
.menu {
  display: flex;
  flex-direction: column;
  border: 2px solid var(--dark);
  background-image: linear-gradient(
      rgba(255, 255, 255, 0.9),
      rgba(255, 255, 255, 0.9)
    ),
    url("../assets/menu.png");
  background-repeat: no-repeat;
  background-size: cover;
  margin: 3em 0 8em 0;
}

.menu-inner {
  text-align: center;
  padding: 2em 1.5em;
}

.menu-inner-text {
  padding: 1em;
}

.pizza {
  display: flex;
  justify-content: space-between;
  padding: 1.7em 0;
}

.menu-img {
  margin: 1em 0;
}

@media only screen and (min-width: 768px) {
  .menu {
    justify-content: center;
    height: 45em;
  }

  .menu-inner {
    width: 80%;
    margin: 0 auto;
  }
}

@media only screen and (min-width: 1024px) {
  .container-menu {
    display: flex;
    height: 100vh;
    position: relative;
  }

  .menu {
    position: absolute;
    bottom: 4em;
    width: 26em;
    height: 32em;
    margin: auto 0 0 0;
    z-index: 100;
  }

  .menu-inner {
    padding: 2em 0 0 0;
  }

  .menu-img {
    position: absolute;
    right: 0;
    object-fit: contain;
    width: 33em;
  }

  .pizza {
    padding: 1.3em 0;
  }
}
</style>