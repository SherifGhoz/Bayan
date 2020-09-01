<template>
  <v-row align="center" justify="space-between">
    <Lottie :options="defaultOptions" :height="600" :width="600" />
  </v-row>
</template>

<script>
import Lottie from 'vue-lottie'
import * as animationData from '~/assets/books.json'

export default {
  components: {
    Lottie
  },
  data() {
    return {
      defaultOptions: { animationData: animationData.default, loop: false }
    }
  }
}
</script>

<style></style>
