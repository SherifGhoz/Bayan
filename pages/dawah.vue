<template>
  <div>
    <Intro />
    <v-divider class="my-8 mx-auto" />
  </div>
</template>

<script>
import Intro from '~/components/Dawah/Intro'

export default {
  components: {
    Intro
  }
}
</script>

<style scoped>
::v-deep.v-divider {
  width: 200px;
}
</style>
