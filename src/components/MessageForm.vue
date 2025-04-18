<template>
  <div class="bottom_container">
    <div>
      <transition name="el-zoom-in-center">
        <h1 v-if="isShown">Send me a<span>Message</span></h1>
      </transition>
    </div>
    <div>
      <transition name="el-zoom-in-center">
        <router-link v-if="isShown" to="/contact"><button>Contact Details</button></router-link>
      </transition>
      <!-- <form @submit.prevent="sendEmail">
        <input v-model="email" placeholder="Email*" />
        <input v-model="message" placeholder="Message*" />
        <button :disabled="isDisabled">Send</button>
      </form> -->
    </div>
  </div>
</template>

<script lang="ts">
import { ElMessage, ElLoading } from 'element-plus'
import axios from 'axios'
const api = 'https://karldelfin.bsite.net'
export default {
  data() {
    return {
      email: '',
      message: '',
      isDisabled: false,
      isShown: false,
    }
  },
  methods: {
    sendEmail() {
      const emailRegex = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$/
      if (this.email == '' || this.message == '') {
        ElMessage.error('Please input required fields!')
        return
      }
      if (!emailRegex.test(this.email)) {
        ElMessage.error('Please enter a valid email address.')
        return
      }
      const loading = ElLoading.service({
        lock: true,
        text: 'Loading',
        background: 'rgba(0, 0, 0, 0.7)',
      })
      this.isDisabled = true
      const payload = {
        email: this.email,
        message: this.message,
      }

      axios
        .post(`${api}/User`, payload)
        .then((response) => {
          ElMessage.success(response.data)
          this.email = ''
          this.message = ''
          loading.close()
          this.isDisabled = false
        })
        .catch((e) => {
          ElMessage.error(e)
          this.email = ''
          this.message = ''
          loading.close()
          this.isDisabled = false
        })
    },
  },
  mounted() {
    setTimeout(() => {
      this.isShown = true
    }, 100)
  },
}
</script>
