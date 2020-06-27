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
          <!-- 画面サイズms以下時 -->
          <div class="hidden-md-and-up">
            <v-card-title class="title font-weight-thin" style="padding:5px 16px 5px">
              Schedule
            </v-card-title>
          </div>
          <!-- 画面サイズ以上時 -->
          <div class="hidden-sm-and-down">
            <v-card-title class="display-1 font-weight-thin" style="padding:5px 16px 5px;">
              Schedule
            </v-card-title>
          </div>
        </v-layout>
        <v-card-text style="padding:0px 16px 0px">
          <hr size="3" class="mb-3">
          <div v-if="schedule.length">
          <div
            v-for="(info, i) in schedule"
            :key="i"
          >
            <!-- 画面サイズms以下時 -->
            <div class="hidden-md-and-up">
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
                <span class="grey--text text--darken-1" :style="infoSpace(info.type)">{{ info.date }}</span><br>
                <p class="subtitle-2" style="margin:0 0 8px">{{ info.content }}</p>
              </div>
              <div v-else>
              </div>
            </div>
            <!-- 画面サイズms以上時 -->
            <div class="hidden-sm-and-down">
              <!-- 表示個数指定 -->
              <div v-if="i<num">
                <v-chip
                  class="ma-2 subtitle-1"
                  outlined
                  :color="chip_color(info.type)"
                  small
                >
                  {{ info.type }}
                </v-chip>
                <span class="subtitle-1 grey--text text--darken-1" :style="infoSpace_2(info.type)">{{ info.date }}</span>
                <span class="subtitle-1" style="margin:0 30px 8px; font-size:1.1rem;">{{ info.content }}</span>
              </div>
              <div v-else>
              </div>
            </div>
          </div>
          </div>
          <div v-else>
            <p class="subtitle-2">本日{{ today[0] }}/{{ today[1] }}時点でライブの予定はありません。</p>
          </div>
          <v-layout justify-center>
            <div style="margin:1rem 0" v-if="num==5">
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
      // type：'info' or 'live' or 'release'
      schedule: [
        {
          type: 'live',
          date: '2020.07.03（金）',
          content: 'タイトル未定　@浅草Gold Sound'
        },
        {
          type: 'live',
          date: '2020.07.14（火）',
          content: 'タイトル未定　@浅草Gold Sounds'
        }
      ],
      info_color: 'blue darken-4',
      live_color: 'orange darken-3',
      release_color: 'light-green darken-3',
    }
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
  },
  computed: {
    infoSpace: function(){
      return function(type){
        if(type == 'info'){
          return {
            'margin-left' : '20px',            
          }
        }
        else if(type == 'live'){
          return {
            'margin-left' : '20px',            
          }
        }
      }
    },
    infoSpace_2: function(){
      return function(type){
        if(type == 'info'){
          return {
            'margin-left' : '45px',            
          }
        }
        else if(type == 'live'){
          return {
            'margin-left' : '48px',            
          }
        }
        else{
          return {
            'margin-left' : '20px',            
          }
        }
      }
    }
  }
}
</script>