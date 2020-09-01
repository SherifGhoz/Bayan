<template>
  <v-slide-y-transition mode="out-in">
    <v-row v-show="show" align="center" justify="space-between">
      <v-col>
        <span class="display-1">
          لوريم ايبسوم دولار سيت أميت ,كونسيكتيتور أدايبا يسكينج أليايت,سيت دو
          أيوسمود تيمبور أنكايديديونتيوت لابوري ات دولار ماجنا أليكيوا . يوت
          انيم أد مينيم فينايم,كيواس نوستريد أكسير سيتاشن يللأمكو لابورأس نيسي
          يت أليكيوب أكس أيا كوممودو كونسيكيوات .
        </span></v-col
      >
      <v-col>
        <Lottie :options="defaultOptions" :height="300" :width="300" />
      </v-col>
    </v-row>
  </v-slide-y-transition>
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
      show: false,
      defaultOptions: { animationData: animationData.default }
    }
  },
  mounted() {
    this.show = true
  }
}
</script>

<style></style>
