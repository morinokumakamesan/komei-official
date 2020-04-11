<template>
  <div class="VueToNuxtLogo">
    <v-col
      md="10"
      offset-md="1"
    >
      <v-card
        flat
      >
        <v-card-title class="title" style="padding:5px 16px 5px">
          News
        </v-card-title>
        <v-card-text style="padding:0px 16px 0px">
          <hr size="3" class="mb-3">
          <div
            v-for="(info, i) in news"
            :key="i"
          >
            <!-- 表示個数は3未満 -->
            <div v-if="i<num">
              <span class="grey--text text--darken-1">{{ info.date }}</span><br>
              <p class="subtitle-2" style="margin:0 0 5px">{{ info.content }}</p>
            </div>
            <div v-else>
            </div>
          </div>
        </v-card-text>
      </v-card>
    </v-col>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  props: ['num'],
  data() {
    return{
      news: [
        {
          date: '2020.04.11',
          content: '孔明オフィシャルサイトを公開しました。'
        },
        {
          date: '2020.04.06',
          content: '孔明ライブ　@渋谷'
        },
        {
          date: '2020.04.05',
          content: '孔明ライブ　@渋谷'
        },
        {
          date: '2020.04.05',
          content: '孔明ライブ　@渋谷'
        },
        {
          date: '2020.04.05',
          content: '孔明ライブ　@渋谷'
        },
      ],
      info: ''
    }
  },
  mounted(){
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(response => (this.info = response))
  }
}
</script>
