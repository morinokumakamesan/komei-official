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
        Profile
      </v-card-title>
      <v-card-text style="padding:0px 16px 0px; white-space:pre-line; word-wrap:break-word;">
        <hr size="3" class="mb-3">
        <p class="subtitle-2">{{ content }}</p>
      </v-card-text>
    </v-card>
    <div class="Triangle Triangle--two" />
    <div class="Triangle Triangle--one" />
    <div class="Triangle Triangle--three" />
    <div class="Triangle Triangle--four" />
  <!-- </v-container> -->
    </v-col>
  </div>
</template>

<script>
export default {
  data() {
    return{
      content: `熊本県出身のシンガーソングライター。ハイトーンの声量おばけ。
      勾玉野郎。夏が好きです。旅や神社巡り、御朱印集めが趣味。都内で活動中。`
    }
  }
}
</script>
