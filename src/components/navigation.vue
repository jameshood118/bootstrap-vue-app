<template>
  <b-nav>
    <template v-for="route in $router.options.routes">
      <b-nav-item
        :key="route.path"
        @click="handleNav(route.name)"
        class="navbar-item"
        v-if="route.path != '*'"
      >
        {{ route.name }}
      </b-nav-item>
    </template>
  </b-nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return { mobileMenu: false, navTheme: 'is-dark' }
  },
  methods: {
    toggleMobileMenu() {
      this.mobileMenu = !this.mobileMenu
    },
    handleNav(name) {
      if (name == this.$route.name) {
        return
      } else {
        if (this.mobileMenu == true) {
          this.mobileMenu = false
        }
        this.$router.push({ name: name })
      }
    }
  }
}
</script>
<style lang="scss" scoped>
.navbar {
  box-shadow: 0 2px 3px rgba(10, 10, 10, 0.1), 0 0 0 1px rgba(10, 10, 10, 0.1);
}
.has-text-light:hover {
  color: black !important;
}

@media screen and (max-width: 1024px - 1px) {
  .navbar.is-fixed-top .navbar-menu,
  .navbar.is-fixed-top-touch .navbar-menu,
  .navbar .navbar-menu {
    overflow: initial;
    padding: 0;
    box-shadow: initial;
    overflow-y: auto;
  }
  .navbar-item {
    &.has-dropdown {
      & .navbar-link::after {
        display: block;
      }
      .navbar-dropdown {
        display: none;
      }
      &.is-active {
        .navbar-dropdown {
          display: block;
        }
      }
    }
  }
  .navbar-burger {
    height: initial;
  }
  .navbar.is-dark {
    .navbar-menu {
      .navbar-item,
      .navbar-item .buttons a {
        color: black !important;
      }
    }
  }
}
</style>
