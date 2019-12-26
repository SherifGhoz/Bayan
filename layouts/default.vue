<template>
  <v-app>
    <v-app-bar fixed app>
      <v-toolbar-title v-text="title" class="ma-auto" />
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
