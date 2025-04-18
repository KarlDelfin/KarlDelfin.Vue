<template>
  <div class="wrapper">
    <div class="company_logo">
      <!-- <figure><img src="./assets/images/my-logo.png" alt="portfolio image" /></figure> -->
      <router-link to="/"
        ><h2>My <span>Portfolio</span></h2></router-link
      >
    </div>
    <NavbarMenu />
    <RouterView />

    <NavbarMenu />
  </div>
</template>

<script lang="ts">
import NavbarMenu from './components/NavbarMenu.vue'
export default {
  components: {
    NavbarMenu,
  },
  data() {
    return {
      activeLink: '',
    }
  },
  methods: {},
  mounted() {},
}
</script>
