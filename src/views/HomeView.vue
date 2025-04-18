<template>
  <div id="banner">
    <div class="banner_container">
      <div class="banner_info">
        <transition name="el-zoom-in-top">
          <h1 v-if="isShown">
            Hello, I'm<span>Karl John T. Delfin<mark>Software Developer</mark></span>
          </h1>
        </transition>
        <transition name="el-zoom-in-top">
          <a v-if="isShown" @click="isShownResume = true">View My Resume</a>
        </transition>
      </div>
      <div>
        <transition name="el-zoom-in-bottom">
          <figure v-if="isShown">
            <img src="../assets/images/me.jpg" alt="my image" /></figure
        ></transition>
      </div>
    </div>
  </div>

  <div id="bottom">
    <MessageForm />
  </div>

  <el-dialog fullscreen v-model="isShownResume">
    <PDFViewer :source="base64" style="height: 90vh; width: 100%" />
  </el-dialog>
</template>

<script lang="ts">
import PDFViewer from 'pdf-viewer-vue'

import MessageForm from '@/components/MessageForm.vue'

export default {
  components: {
    MessageForm,
    PDFViewer,
  },
  data() {
    return {
      file: '/public/Delfin-Karl-CV.pdf',
      base64: 'Delfin-Karl-CV.pdf',
      isShown: false,
      isShownResume: false,
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
