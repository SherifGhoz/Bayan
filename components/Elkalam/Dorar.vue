<template>
  <div class="pa-8 text-center">
    <v-card
      v-for="(hadith, index) in result"
      :key="index"
      v-html="hadith"
      class="pa-4 ma-4"
    ></v-card>
    <v-btn :href="readMoreLink" color="primary" x-large>اقرأ المزيد</v-btn>
  </div>
</template>

<script>
export default {
  data() {
    return {
      result: null,
      searchQuery: ''
    }
  },
  computed: {
    readMoreLink() {
      return `https://dorar.net/hadith/search?q=${this.searchQuery}`
    }
  },
  mounted() {
    this.getData()
  },
  methods: {
    getData() {
      this.$jsonp('https://dorar.net/dorar_api.json', {
        skey: 'بني الإسلام'
      })
        .then((json) => {
          const hadiths = json.ahadith.result.split('--------------')
          hadiths.pop()
          this.result = hadiths
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>

<style></style>
