<template>
  <v-app>
    <v-app-bar fixed app>
      <v-toolbar-title v-text="title" />
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      title: 'بيان'
    }
  }
}
</script>

<style>
.v-application {
  font-family: Tajawal, Arial, Helvetica, sans-serif;
  text-align: center;
}
</style>
