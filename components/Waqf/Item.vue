<template>
  <v-hover v-slot:default="{ hover }">
    <v-card :width="400" :height="400" :elevation="hover ? 12 : 2">
      <v-slide-y-reverse-transition mode="out-in">
        <v-sheet v-if="hover" tile class="item-info pa-4">
          <v-row align="center">
            <v-col cols="12" sm="10">
              <h3>اسم الكتاب: {{ item.title }}</h3>
              <h3>الناشر: {{ item.publisher }}</h3>
              <h4>تاريخ النشر: {{ item.publicationDate }}</h4>
              <h3>{{ item.text }}</h3>
              <h3>{{ item.subtext }}</h3>
            </v-col>
            <v-col cols="12" sm="2">
              <v-tooltip top>
                <template v-slot:activator="{ on, attrs }">
                  <v-btn v-bind="attrs" v-on="on" color="primary" icon>
                    <v-icon>mdi-cart-plus</v-icon>
                  </v-btn>
                </template>
                <div class="request-tooltip pa-2">طلب</div>
              </v-tooltip>
            </v-col>
          </v-row>
        </v-sheet>
      </v-slide-y-reverse-transition>
      <v-img :src="item.img" width="100%" height="100%"> </v-img>
    </v-card>
  </v-hover>
</template>
<script>
export default {
  data: () => ({
    item: {
      title: 'فتح الباري',
      publisher: 'دار الكتب العلمية',
      publicationDate: '2018',
      text: 'نص اختياري',
      subtext: 'نص اختياري',
      img: require('~/assets/Fatholbari.jpg')
    }
  })
}
</script>
<style scoped>
.item-info {
  position: absolute;
  width: 100%;
  bottom: 0;
  left: 0;
  z-index: 3;
}

.request-tooltip {
  font-size: 2rem;
}
</style>
