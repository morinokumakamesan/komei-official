<template style="background-color: #000000">
  <v-layout
    column
    justify-center
  >
    <div class="text-center hidden-md-and-up">
      <v-img
        width="100%"
        height="250px"
        :src=img_news
        decoding="async"
      >
      </v-img>
    </div>
    <v-col
      md="10"
      offset-md="1"
      class="hidden-sm-and-down"
    >
      <v-img
        width="100%"
        height="700px"
        :src=img_news
        decoding="async"
      >
      </v-img>
    </v-col>
    <mainNews :num=100 />
  </v-layout>
</template>

<script>
import mainNews from '~/components/mainNews.vue'
export default {
  components: {
    mainNews,
  },
  data() {
    return {
      title: '杉本孔明',
      img_news: require('../assets/images/news.jpg')
    }
  },
}
</script>
