<template>
  <header :class="{ 'scrolled-nav': scrolledNav }">
    <nav>
      <div class="branding">
        <img src="../assets/logo.png" alt="" />
      </div>

      <ul v-show="!mobile" class="navigation">
        <li>
          <router-link class="link" :to="{ name: 'Home' }">Home</router-link>
        </li>
        <li>
          <router-link class="link" :to="{ name: 'About' }">About</router-link>
        </li>
        <li>
          <router-link class="link" :to="{ name: '' }">Portfolio</router-link>
        </li>
        <li>
          <router-link class="link" :to="{ name: '' }">Contact</router-link>
        </li>
      </ul>
      <div class="icon" :class="{ 'icon-mobile': mobileNav }">
        <i
          @click="toggleMobileNav"
          v-show="mobile"
          class="far fa-bars"
          :class="{ 'icon-active': mobileNav }"
        ></i>
      </div>
      <transition name="mobile-nav">
        <ul v-show="mobileNav" class="dropdown-nav">
          <li @click="closeMobileNav">
            <router-link class="link" :to="{ name: 'Home' }">Home</router-link>
          </li>
          <li @click="closeMobileNav">
            <router-link class="link" :to="{ name: 'About' }"
              >About</router-link
            >
          </li>
          <li @click="closeMobileNav">
            <router-link class="link" :to="{ name: '' }">Portfolio</router-link>
          </li>
          <li @click="closeMobileNav">
            <router-link class="link" :to="{ name: '' }">Contact</router-link>
          </li>
        </ul>
      </transition>
    </nav>
  </header>
</template>

<script>
export default {
  name: "navigation",
  data() {
    return {
      scrolledNav: null,
      mobile: null,
      mobileNav: null,
      windowWidth: null,
    };
  },
  created() {
    window.addEventListener("resize", this.checkScreen);
    this.checkScreen();
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
  methods: {
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav;
    },

    updateScroll() {
      const scrollPosition = window.scrollY;
      if (scrollPosition > 50) {
        this.scrolledNav = true;
        return;
      }
      this.scrolledNav = false;
    },

    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 750) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
      return;
    },

    closeMobileNav() {
      return (this.mobileNav = false);
    },
  },
};
</script>

<style scoped>
header {
  width: 100%;
  position: fixed;
  z-index: 99;
  transition: 0.5s ease all;
  color: #fff;
}

header nav {
  position: relative;
  display: flex;
  transition: 0.5s ease all;
  width: 100%;
  margin: 0 auto;
}

@media (min-width: 1140px) {
  header nav {
    max-width: 1140px;
  }
}

header nav ul,
header nav .link {
  font-weight: 500;
  color: #fff;
  list-style: none;
  text-decoration: none;
}

header nav li {
  padding: 16px;
  margin-left: 16px;
}

header nav .link {
  font-size: 1rem;
  transition: 0.5s ease all;
  padding-bottom: 4px;
  border-bottom: 1px solid transparent;
}

header nav .link:hover {
  color: var(--primary);
  text-decoration: line-through;
  text-decoration-color: var(--primary);
}

header nav .branding {
  position: relative;
  left: 50%;
  transform: translateX(-50%);
  z-index: 16;
}

header nav .branding img {
  width: 8em;
  transition: 0.5s ease all;
}

header nav .navigation {
  display: flex;
  align-items: center;
  flex: 1;
  justify-content: flex-end;
}

header nav .icon {
  display: flex;
  align-items: center;
  position: absolute;
  top: 0;
  right: 0;
  background: var(--dark);
  padding: 1.5em;
  z-index: 15;
}

.icon.icon-mobile {
  background: var(--light);
}

header nav .icon i {
  font-size: 24px;
  transition: 0.8s ease all;
  cursor: pointer;
  color: var(--light);
}

header nav .icon-active {
  transform: rotate(180deg);
}

.fa-bars:before {
  color: var(--primary);
}

header nav .dropdown-nav {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  position: fixed;
  width: 100%;
  height: 100%;
  background-image: linear-gradient(rgba(0, 0, 0, 0.9), rgba(0, 0, 0, 0.9)),
    url("../assets/menu-white.jpg");
  background-size: cover;
  top: 0;
  left: 0;
}

header nav .dropdown-nav li {
  margin-left: 0;
}

header nav .dropdown-nav li .link {
  font-family: droid-sans-mono, monospace;
  color: #fff;
}

header nav .mobile-nav-enter-active,
header nav .mobile-nav-leave-active {
  transition: 1s ease all;
}

header nav .mobile-nav-enter-from,
header nav .mobile-nav-leave-to {
  transform: translateX(-100%);
}

header nav .mobile-nav-enter-to {
  transform: translateX(0);
}

.scrolled-nav {
  background: #000;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
    0 2px 4px -1px rgba(0, 0, 0, 0.06);
}

.scrolled-nav nav {
  padding: 8px 0;
}

.scrolled-nav nav .branding img {
  width: 40px;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
    0 2px 4px -1px rgba(0, 0, 0, 0.06);
}
</style>
