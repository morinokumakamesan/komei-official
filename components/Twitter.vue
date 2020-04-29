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
          <v-card-title class="title" style="padding:5px 16px 5px">
            Twitter
          </v-card-title>
        </v-layout>
        <v-card-text style="padding:0px 16px 0px">
          <hr size="3" class="mb-3">
          <a class="twitter-timeline" data-lang="en" data-chrome="nofooter" data-height="400" data-weight="70" href="https://twitter.com/sugissw?ref_src=twsrc%5Etfw">Tweets by sugissw</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
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