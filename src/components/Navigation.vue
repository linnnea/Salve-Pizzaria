<template>
  <header :class="{ 'scrolled-nav': scrolledNav }">
    <nav>
      <!-- <div v-if="mobile" class="branding"> -->
        <router-link :to="{ path: '/hero', hash: '#home' }" v-if="mobile" class="branding">
          <img src="../assets/logo.png" alt="" />
        </router-link>
      <!-- </div> -->

      <ul v-if="!mobile" class="navigation">
        <li>
          <router-link class="link" :to="{ path: '/menu', hash: '#section-menu' }">Menu</router-link>
        </li>
        <li>
          <router-link class="link" :to="{ path: '/reservations', hash: '#section-reservations' }">Reservations</router-link>
        </li>

         <router-link :to="{ path: '/hero', hash: '#home' }" class="branding">
          <img src="../assets/logo.png" alt="" />
        </router-link>

        <li>
          <router-link class="link" :to="{ path: '/openinghours', hash: '#section-openinghours' }">Opening Hours</router-link>
        </li>
        <li>
          <router-link class="link" :to="{ path: '/location', hash: '#section-contact' }">Contact</router-link>
        </li>
      </ul>
      <div v-if="mobile" class="icon" :class="{ 'icon-mobile': mobileNav }">
        <i
          @click="toggleMobileNav"
          v-if="mobile"
          class="far fa-bars"
          :class="{ 'icon-active': mobileNav }"
        ></i>
      </div>
      <transition name="mobile-nav">
        <ul v-if="mobileNav" class="dropdown-nav">
          <li @click="closeMobileNav">
            <router-link class="link" :to="{ path: '/menu', hash: '#section-menu' }">Menu</router-link>
          </li>
          <li @click="closeMobileNav">
            <router-link class="link" :to="{ path: '/reservations', hash: '#section-reservations' }">Reservations</router-link>
          </li>
          <li @click="closeMobileNav">
            <router-link class="link" :to="{ path: '/openinghours', hash: '#section-openinghours' }">Opening Hours</router-link>
          </li>
          <li @click="closeMobileNav">
            <router-link class="link" :to="{ path: '/location', hash: '#section-contact' }">Contact</router-link>
          </li>
        </ul>
      </transition>
    </nav>
  <router-view/>
  </header>
</template>

<script>
export default {
  name: "Navigation",
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
  watch: {
    mobileNav: function () {
      if (this.mobileNav) {
        document.documentElement.style.overflow = "hidden";
        return;
      }

      document.documentElement.style.overflow = "auto";
    },
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
  justify-content: center;
  transition: 0.5s ease all;
  width: 100%;
  margin: 0 auto;
}

@media (min-width: 1140px) {
  header nav {
    max-width: 1140px;
  }
}

header nav ul {
  border-bottom: 1px solid var(--dark);
  padding: 0.3em;
}

header nav ul,
header nav .link {
  font-weight: 500;
  color: var(--dark);
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
  cursor: pointer;
}

header nav .link:hover {
  color: var(--primary);
  text-decoration: line-through;
  text-decoration-thickness: 3px;
  text-decoration-style: wavy;
  text-decoration-color: var(--primary);
}

header nav .branding {
  position: relative;
}

header nav .branding img {
  width: 8em;
  transition: 0.5s ease all;
}

header nav .navigation {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  flex: 1;
}

header nav .icon {
  display: flex;
  align-items: center;
  position: absolute;
  top: 0;
  right: 0;
  background: var(--dark);
  padding: 1.5em;
  transition: 0.5s ease all;
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
  transform: translateX(-100%);
}

header nav .mobile-nav-enter-from,
header nav .mobile-nav-leave-to {
  transform: translateX(-100%);
}

header nav .mobile-nav-enter-to {
  transform: translateX(0);
}

.scrolled-nav nav {
  padding: 0;
  height: 3em;
}

@media (min-width: 1140px) {
  .scrolled-nav .link {
    font-size: 0.6rem;
  }
  .scrolled-nav .icon {
    padding: 0.4em 0.8em;
  }

  .scrolled-nav nav .branding img {
    width: 4em;
  }
}
</style>
