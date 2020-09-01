<template>
  <div class="pa-8 text-center">
    <v-text-field
      :value="query"
      @input="handleSearch"
      @click:clear="clearQuery"
      filled
      outlined
      prepend-inner-icon="mdi-magnify"
      clear-icon="mdi-close-circle"
      clearable
      label="ادخل كلمة من الحديث"
      type="text"
      single-line=""
    ></v-text-field>
    <v-card
      v-for="(hadith, index) in result"
      :key="index"
      v-html="hadith"
      class="pa-4 my-4"
    ></v-card>
    <v-btn :href="readMoreLink" color="primary" x-large>اقرأ المزيد</v-btn>
  </div>
</template>

<script>
export default {
  data() {
    return {
      result: null,
      query: ''
    }
  },
  computed: {
    readMoreLink() {
      return `https://dorar.net/hadith/search?q=${this.query}`
    }
  },

  methods: {
    handleSearch() {
      this.getData()
      console.log('sljdnsdjkfn')
    },
    getData() {
      this.$jsonp('https://dorar.net/dorar_api.json', {
        skey: this.query
      })
        .then((json) => {
          const hadiths = json.ahadith.result.split('--------------')
          hadiths.pop()
          this.result = hadiths
        })
        .catch((err) => {
          console.log(err)
        })
    },
    clearQuery() {
      this.query = ''
    }
  }
}
</script>

<style></style>
