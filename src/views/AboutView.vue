<template>
  <div id="about">
    <div class="about_container">
      <transition name="el-zoom-in-bottom">
        <figure v-if="isShown">
          <img src="../assets/images/me.jpg" alt="my image" /></figure
      ></transition>
      <transition name="el-zoom-in-left">
        <h1 v-if="isShown">About <span>Karl John T. Delfin</span></h1>
      </transition>

      <transition name="el-zoom-in-left">
        <p v-if="isShown">
          A flexible and adaptive individual with good programming skills. With a history in
          developing web applications through internship and freelancing, ready to work with
          multiple projects. Ready to grab an opportunity to grow and enhance skills. A graduated
          Bachelor Science in Information Technology from
          <a
            href="https://www.google.com/maps?sca_esv=2b989cd38cfe142e&output=search&q=university+of+cebu&source=lnms&fbs=ABzOT_CWdhQLP1FcmU5B0fn3xuWpA-dk4wpBWOGsoR7DG5zJBjnSuuKZNj-6zieDk_gkn6AKnSLKCogWmTELYC4Vpj6glgVYzC6vXjqFNAPtxDPMUvtbFPaUc1rK5eGyWVQT6-97Bi1TB27gIgmvESxfzyt-wnGix44jX9UY-Lyv-Ubm7qsATgT-hXOxWJmZgSNAbDKJ4_DJmYC8y_i48nidvtymzjF46w&entry=mc&ved=1t:200715&ictx=111"
            target="_blank"
            >University of Cebu</a
          >-College of Computer Studies.
        </p>
      </transition>
      <h2>My Projects</h2>
      <ul>
        <li>
          <a href="https://ambitious-tree-081bf0b0f.6.azurestaticapps.net/" target="_blank"
            >Calendar</a
          >
        </li>
        <li>Visitor System</li>
        <li>
          <a href="https://ashy-moss-0c2834e00.6.azurestaticapps.net/timetracker" target="_blank"
            >Time Tracker</a
          >
        </li>
        <li>
          <a href="https://green-ocean-01ebbf20f.6.azurestaticapps.net/" target="_blank"
            >TExtractImage</a
          >
        </li>
      </ul>
      <p>You can contact me by clicking <router-link to="/contact">Here</router-link></p>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      isShown: false,
    }
  },
  methods: {},
  mounted() {
    setTimeout(() => {
      this.isShown = true
    }, 100)
  },
}
</script>
