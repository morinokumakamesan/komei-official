<template>
  <div class="VueToNuxtLogo" style="background-color:#E6E6E6">
    <v-col
      md="10"
      offset-md="1"
    >
      <v-card
        flat
        color="#E6E6E6"
      >
        <v-layout justify-center>
          <v-card-title class="title" style="padding:5px 16px 5px">
            News
          </v-card-title>
        </v-layout>
        <v-card-text style="padding:0px 16px 0px">
          <hr size="3" class="mb-3">
          <div
            v-for="(info, i) in news"
            :key="i"
          >
            <!-- 表示個数指定 -->
            <div v-if="i<num">
              <v-chip
                class="ma-2"
                outlined
                :color="chip_color(info.type)"
                small
              >
                {{ info.type }}
              </v-chip>
              <span class="grey--text text--darken-1">{{ info.date }}</span><br>
              <p class="subtitle-2" style="margin:0 0 8px">{{ info.content }}</p>
            </div>
            <div v-else>
            </div>
          </div>
          <v-layout justify-center>
            <div style="margin:1rem 0" v-if="num==5">
              <v-btn
                color="real darken-1"
                despressed
                outlined
                to="news"
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
import axios from 'axios'
export default {
  props: ['num'],
  data() {
    return{
      news: [
        {
          type: 'info',
          date: '2020.04.11（土）',
          content: '孔明オフィシャルサイトを公開しました。'
        },
        {
          type: 'live',
          date: '2020.04.06（月）',
          content: '孔明ライブ　@浅草GoldSounds'
        },
        {
          type: 'release',
          date: '2020.04.05（日）',
          content: 'New Single「〇〇〇〇」'
        },
      ],
      info_color: 'blue darken-4',
      live_color: 'orange darken-3',
      release_color: 'light-green darken-3',
    }
  },
  mounted(){
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(response => (this.info = response))
  },
  methods: {
    chip_color(type){
      if(type == 'info'){
        return this.info_color
      }
      else if(type == 'live'){
        return this.live_color
      }
      else if(type == 'release'){
        return this.release_color
      }
    }
  }
}
</script>
