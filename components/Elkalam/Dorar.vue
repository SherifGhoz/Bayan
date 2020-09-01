<template>
  <div class="pa-8">
    <div v-html="result"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      result: null
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
          this.result = json.ahadith.result
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>

<style></style>
