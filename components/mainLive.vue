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
      <v-card-title class="title" style="padding:5px 16px 5px">
        Live
      </v-card-title>
      <v-card-text style="padding:0px 16px 0px">
        <hr size="3" class="mb-3">
        <div
          v-for="(info, i) in news"
          :key="i"
        >
          <span class="grey--text text--darken-1">{{ info.date }}</span><br>
          <p class="subtitle-2">{{ info.content }}</p>
        </div>
      </v-card-text>
    </v-card>
    <div class="Triangle Triangle--two" />
    <div class="Triangle Triangle--one" />
    <div class="Triangle Triangle--three" />
    <div class="Triangle Triangle--four" />
    </v-col>
  <!-- </v-container> -->
  </div>
</template>

<script>
export default {
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
  }
}
</script>