<template>
  <v-app>
    <v-app-bar :height="90" color="primary" prominent flat app>
      <h1 class="white--text mx-auto">{{ title }}</h1>
    </v-app-bar>
    <v-main>
      <div class="white">
        <v-container class="pa-0">
          <NavTabs />
        </v-container>
      </div>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import NavTabs from '~/components/layout/NavTabs'
export default {
  components: {
    NavTabs
  },
  data() {
    return {
      title: 'بيان'
    }
  }
}
</script>
<style>
h1 {
  font-family: Tajawal, Arial, Helvetica, sans-serif;
  font-size: 60px;
}
h2 {
  font-size: 60px;
}
</style>
