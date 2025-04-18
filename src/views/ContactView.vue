<template>
  <div id="contact">
    <div class="contact_container">
      <transition name="el-zoom-in-left">
        <h1 v-if="isShown">Contact<span>Details</span></h1>
      </transition>
      <el-collapse accordion>
        <el-collapse-item title="Email" name="1">
          <div class="contact_info">
            Send me an email to
            <a href="mailto:dkhrl2000@gmail.com" target="_blank">dkhrl2000@gmail.com</a>
          </div>
        </el-collapse-item>
        <el-collapse-item title="Facebook" name="2">
          <div class="contact_info">
            Drop me a message on
            <a href="https://m.me/dkhrl" target="_blank">facebook</a>
          </div>
        </el-collapse-item>
      </el-collapse>
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
