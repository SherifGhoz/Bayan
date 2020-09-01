<template>
  <v-row align="center" justify="space-between">
    <v-col>
      <span class="display-1">
        لوريم ايبسوم دولار سيت أميت ,كونسيكتيتور أدايبا يسكينج أليايت,سيت دو
        أيوسمود تيمبور أنكايديديونتيوت لابوري ات دولار ماجنا أليكيوا . يوت انيم
        أد مينيم فينايم,كيواس نوستريد أكسير سيتاشن يللأمكو لابورأس نيسي يت
        أليكيوب أكس أيا كوممودو كونسيكيوات .
      </span></v-col
    >
    <v-col>
      <Lottie :options="defaultOptions" :height="300" :width="300" />
    </v-col>
  </v-row>
</template>

<script>
import Lottie from 'vue-lottie'
import * as animationData from '~/assets/teacher.json'

export default {
  components: {
    Lottie
  },
  data() {
    return {
      defaultOptions: { animationData: animationData.default }
    }
  }
}
</script>

<style></style>
