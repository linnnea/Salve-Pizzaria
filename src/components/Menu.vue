<template>
  <div>
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
      <img src="../../public/img/menu.jpg" alt="" />
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
  border: 1px solid var(--dark);
  background-image: linear-gradient(
      rgba(255, 255, 255, 0.9),
      rgba(255, 255, 255, 0.9)
    ),
    url("../../public/img/menu.png");
  background-repeat: no-repeat;
  background-size: cover;
  margin: 1em;
}

.menu-inner {
  text-align: center;
  padding: 2em;
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
  margin: 1em;
}
</style>