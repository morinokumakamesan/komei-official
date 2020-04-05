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
      <v-card-title class="headline">
        News
      </v-card-title>
      <v-card-text>
        <hr size="3" class="mb-3">
        <div
          v-for="(info, i) in news"
          :key="i"
        >
          <span class="grey--text text--darken-1">{{ info.date }}</span><br>
          <p style="font-size: 17px;">{{ info.content }}</p>
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
          date: '2020.04.05',
          content: '孔明ライブ　@渋谷'
        },
        {
          date: '2020.04.06',
          content: '孔明ライブ　@渋谷'
        }
      ]
    }
  }
}
</script>
