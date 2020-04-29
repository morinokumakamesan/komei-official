<template>
  <div class="VueToNuxtLogo">
  <!-- <v-container> -->
    <v-col
      md="10"
      offset-md="1"
    >
      <v-card
        flat
      >
        <v-layout justify-center>
          <v-card-title class="title" style="padding:5px 16px 5px">
            Schedule
          </v-card-title>
        </v-layout>
        <v-card-text style="padding:0px 16px 0px">
          <hr size="3" class="mb-3">
          <div v-if="news.length">
            <div
              v-for="(info, i) in news"
              :key="i"
            >
              <span class="grey--text text--darken-1">{{ info.date }}</span><br>
              <p class="subtitle-2" style="margin:0 0 8px">{{ info.content }}</p>
            </div>
          </div>
          <div v-else>
            <p class="subtitle-2">本日{{ today[0] }}/{{ today[1] }}時点でライブの予定はありません。</p>
          </div>
          <v-layout justify-center>
            <div style="margin:1rem 0" v-if="num==3">
              <v-btn
                color="real darken-1"
                despressed
                outlined
                to="schedule"
              >
                More
              </v-btn>
            </div>
          </v-layout>
        </v-card-text>
      </v-card>
    </v-col>
  </div>
</template>

<script>
export default {
  props: ['today'],
  props: ['num'],
  data() {
    return{
      news: [
        {
          date: '2020.04.17',
          content: '孔明ライブ　@浅草Gold Sound'
        },
        {
          date: '2020.05.02',
          content: '孔明ライブ　@浅草Gold Sounds'
        },
        {
          date: '2020.07.14',
          content: '孔明ライブ　@浅草Gold Sounds'
        }
      ]
    }
  },
}
</script>