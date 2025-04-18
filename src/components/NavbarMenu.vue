<template>
  <div class="wrapper">
    <div id="navbar">
      <div class="navbar_container">
        <router-link to="/" :class="{ active: activeLink === '/' }">Home</router-link>
        <router-link to="/about" :class="{ active: activeLink === '/about' }">About</router-link>
        <router-link to="/contact" :class="{ active: activeLink === '/contact' }"
          >Contact Me</router-link
        >
      </div>
      <div class="social_media">
        <a href="https://www.facebook.com/dkhrl" target="_blank">
          <img src="../assets/images/facebook.png" alt="facebook" />
        </a>
        <a href="https://www.linkedin.com/in/karl-delfin-33b3b22a4/" target="_blank" alt="linkedin">
          <img src="../assets/images/linkedin.png" />
        </a>
        <a href="mailto:dkhrl2000@gmail.com" target="_blank" alt="gmail">
          <img src="../assets/images/gmail.png" />
        </a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      activeLink: this.$route.path,
    }
  },
  watch: {
    $route(to) {
      this.activeLink = to.path
    },
  },
  mounted() {
    this.activeLink = this.$route.path
  },
}
</script>

<style scoped>
a.active {
  text-decoration: underline;
  font-weight: bold; /* Optional: Add bold for emphasis */
}
</style>
