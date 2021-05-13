<template>
  <div id="app">
    <Header />
    <Hero />
    <Intro />
    <Menu />
    <Reservations />
    <Gallery />
    <OpeningHours />
    <Location />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header";
import Hero from "./components/Hero";
import Intro from "./components/Intro";
import Menu from "./components/Menu";
import Reservations from "./components/Reservations";
import Gallery from "./components/Gallery";
import OpeningHours from "./components/OpeningHours";
import Location from "./components/Location";
import Footer from "./components/Footer";

export default {
  name: "App",
  components: {
    Header,
    Hero,
    Intro,
    Menu,
    Reservations,
    Gallery,
    OpeningHours,
    Location,
    Footer,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  background: #f0eee8;
  color: var(--dark);
  height: 100vh;
}

h1 {
  color: var(--primary);
}

img {
  display: block;
  max-width: 100%;
}

:root {
  --primary: #a54e4e;
  --dark: #2c2c2c;
  --light: #fff;
}
</style>
