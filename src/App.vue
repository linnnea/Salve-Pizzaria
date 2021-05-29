<template>
  <div id="app">
    <Navigation />
    <Hero />
    <Intro class="fadein" />
    <Menu class="fadein" />
    <Reservations class="fadein" />
    <Gallery class="fadein" />
    <OpeningHours class="fadein" />
    <Location class="fadein" />
    <Footer class="fadein" />
  </div>
</template>

<script>
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

import Navigation from "./components/Navigation";
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
    Navigation,
    Hero,
    Intro,
    Menu,
    Reservations,
    Gallery,
    OpeningHours,
    Location,
    Footer
  },
  mounted() {
    gsap.utils.toArray(".fadein").forEach(anim => {
      gsap.from(anim, {
        scrollTrigger: {
          start: "top center",
          end: "top 100%",
          scrub: 1,
          trigger: anim,
        },
      y: 50,
      opacity: 0,
      ease: 'Power2.inOut',
      duration: 3,
      })
    })
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background: var(--bg);
  font-family: droid-sans-mono, monospace;
}
#app {
  color: var(--dark);
  min-height: 100vh;
  position: relative;
  background-color: #f1f1f1;
}
h1 {
  text-transform: uppercase;
  color: var(--primary);
}
h1,
h2,
h3,
h4,
h5 {
  font-family: mono45-headline, monospace;
}
img {
  display: block;
  max-width: 100%;
}
:root {
  /* Breaking points */
  --tablet: 768px;
  --small: 1024px;
  --large: 1366px;
  --xl: 1920px;
  /* Colors */
  --primary: #d44e48;
  --bg: #eee4db;
  --dark: #2c2c2c;
  --light: #fff;
}
.container {
  margin: 0 auto;
  width: 90%;
}
[id*="section-"] {
  padding-top: 4em;
}
@media only screen and (min-width: 768px) {
  .container {
    width: 80%;
    max-width: 55em;
  }
}

@media only screen and (min-width: 1024px) {
  [id*="section-"] {
    padding-top: 6em;
  }
}
</style>