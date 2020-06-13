<template>
  <div class="VueToNuxtLogo" style="background-color:#E6E6E6">
  <!-- <v-container> -->
    <v-col
      md="10"
      offset-md="1"
    >
      <v-card
        flat
        color="#E6E6E6"
      >
        <v-layout justify-center>
          <!-- 画面サイズms以下時のヘッダー -->
          <div class="hidden-md-and-up">
            <v-card-title class="title font-weight-thin" style="padding:5px 16px 5px">
              Twitter
            </v-card-title>
          </div>
          <!-- 画面サイズ以上時のヘッダー -->
          <div class="hidden-sm-and-down">
            <v-card-title class="display-1 font-weight-thin" style="padding:5px 16px 5px">
              Twitter
            </v-card-title>
          </div>
        </v-layout>
        <v-card-text style="text-align: center; padding:0px 16px 0px;">
          <hr size="3" class="mb-3">

          <!-- 画面サイズms以下時のヘッダー -->
          <div class="hidden-md-and-up">
            <a class="twitter-timeline" data-lang="en" data-chrome="nofooter" data-height="400" href="https://twitter.com/sugissw?ref_src=twsrc%5Etfw">Tweets by sugissw</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
          </div>

          <!-- 画面サイズms以上時のヘッダー -->
          <div class="hidden-sm-and-down">
            <a class="twitter-timeline" data-lang="en" data-chrome="nofooter" data-height="500" data-width="600" href="https://twitter.com/sugissw?ref_src=twsrc%5Etfw">Tweets by sugissw</a>
          </div>

        </v-card-text>
      </v-card>
    </v-col>
  </div>
</template>

<script>
export default {
  props: ['today'],
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