<template>
  <v-tabs v-model="activeTab" :height="90" fixed-tabs icons-and-text optional>
    <v-tab to="/dawah">
      <span>بيان الدعوية</span>
      <v-icon>mdi-islam</v-icon>
    </v-tab>
    <v-tab key="elmiah" to="/elmiah">
      <span>بيان العلمية</span>
      <v-icon>mdi-lightbulb-on-outline</v-icon>
    </v-tab>
    <v-tab key="library" to="/library">
      <span>مكتبة بيان</span>
      <v-icon>mdi-library</v-icon>
    </v-tab>
    <v-tab key="elkalam" to="/elkalam">
      <span>الكلام دا صح؟</span>
      <v-icon>mdi-comment-question-outline</v-icon>
    </v-tab>
    <v-tab key="waqf" to="/waqf">
      <span>الوقف العلمي</span>
      <v-icon>mdi-book-multiple</v-icon>
    </v-tab>
  </v-tabs>
</template>

<script>
export default {
  computed: {
    activeTab() {
      return this.$route.name
    }
  }
}
</script>

<style>
.v-tabs-bar .v-tab > * {
  font-family: Scheherazade, Arial, Helvetica, sans-serif;
  font-size: 28px;
  margin-bottom: 0 !important;
}
</style>
