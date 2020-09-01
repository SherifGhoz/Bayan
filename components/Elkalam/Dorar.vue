<template>
  <div class="pa-8 text-center">
    <v-text-field
      :value="query"
      @input="handleSearch($event)"
      @click:clear="clearQuery"
      filled
      outlined
      prepend-inner-icon="mdi-magnify"
      clear-icon="mdi-close-circle"
      clearable
      label="ادخل كلمة من الحديث"
      type="text"
      single-line
    ></v-text-field>
    <v-card
      v-for="(hadith, index) in result"
      :key="index"
      v-html="hadith"
      class="pa-4 my-4"
    ></v-card>
    <v-progress-circular
      v-if="loading"
      :size="50"
      color="primary"
      indeterminate
    ></v-progress-circular>
    <v-btn
      v-if="result"
      :href="readMoreLink"
      target="_blank"
      color="primary"
      x-large
      >اقرأ المزيد</v-btn
    >
  </div>
</template>

<script>
import debounce from 'lodash/debounce'
export default {
  data() {
    return {
      result: null,
      loading: false,
      query: ''
    }
  },
  computed: {
    readMoreLink() {
      return `https://dorar.net/hadith/search?q=${this.query}`
    }
  },
  methods: {
    handleSearch(val) {
      this.result = null
      this.loading = true
      this.query = val
      this.getData()
    },
    getData: debounce(function() {
      const query = this.query
      this.$jsonp('https://dorar.net/dorar_api.json', {
        skey: query
      })
        .then((json) => {
          const hadiths = json.ahadith.result.split('--------------')
          if (hadiths.length > 1) {
            hadiths.pop()
            this.result = hadiths
          }
        })
        .catch((err) => {
          console.log(err)
        })
      this.loading = false
    }, 300),
    clearQuery() {
      this.query = ''
    }
  }
}
</script>

<style></style>
