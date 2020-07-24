<template>
  <v-container>
    <v-tabs v-model="tab" :height="100" background-color="primary" grow="" dark>
      <v-tab>الدرر السنية</v-tab>
      <v-tab>الكلام دا صح؟</v-tab>
    </v-tabs>
    <v-tabs-items v-model="tab">
      <v-tab-item><Dorar /></v-tab-item>
      <v-tab-item>الكلام دا صح ؟</v-tab-item>
    </v-tabs-items>
  </v-container>
</template>

<script>
import Dorar from '@/components/Elkalam/Dorar'

export default {
  components: {
    Dorar
  },
  data() {
    return {
      tab: null
    }
  }
}
</script>

<style scoped>
/deep/.v-tab {
  font-family: Scheherazade, Arial, Helvetica, sans-serif;
  font-size: 3rem;
  font-weight: bold;
  letter-spacing: 0.1rem;
}
</style>
