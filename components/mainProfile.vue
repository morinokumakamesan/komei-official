<template>
  <div class="VueToNuxtLogo" style="background-color: #E6E6E6">
  <!-- <v-container> -->
    <v-col
      md="10"
      offset-md="1"
    >
      <v-card
        class="pb-10"
        flat
        color="#E6E6E6"
      >
        <v-layout justify-center>
          <!-- 画面サイズms以下時 -->
          <div class="hidden-md-and-up">
            <v-card-title class="title font-weight-thin" style="padding:5px 16px 5px; margin:5px 0px 5px;">
              Profile
            </v-card-title>
          </div>
          <!-- 画面サイズms以上時 -->
          <div class="hidden-sm-and-down">
            <v-card-title class="display-1 font-weight-thin" style="padding:5px 16px 5px; margin:30px 0px 20px;">
              Profile
            </v-card-title>
          </div>
        </v-layout>
        <v-card-text style="padding:0px 16px 0px; white-space:pre-line; word-wrap:break-word;">
          <hr size="3" class="mb-3">
            <!-- 画面サイズms以下時 -->
            <div class="hidden-md-and-up">
              <div class="subtitle-2">{{ content }}</div>
            </div>
            <!-- 画面サイズms以上時 -->
            <div class="hidden-sm-and-down">
              <div class="subtitle-1">{{ content }}</div>
            </div>
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
