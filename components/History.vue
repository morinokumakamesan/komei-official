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
          History
        </v-card-title>
        <v-card-text style="white-space:pre-line; word-wrap:break-word;">
          <hr size="3" class="mb-3">
          <div
            v-for="(history, i) in histories"
            :key="i"
          >
            <v-row
              class="subtitle-2"
            >
            <v-col
              v-for="n in 2"
              :key="n"
              :cols="n === 1 ? 4 : 8"
              style="padding: 0px 5px 5px 12px;"
            >
              <v-card
                flat
              >
                {{ n === 1 ? history.year : history.content }}
              </v-card>
            </v-col>

              <!-- <v-col
                md="2"
                sm="4"
                xs="4"
              >
                <v-card
                  class="pa-2 subtitle-1"
                  flat
                >
                {{ cols }}
                  {{ history.year }}
                </v-card>
              </v-col>
              <v-col
                md="10"
                sm="4"
                xs="4"
              >
                <v-card
                  class="pa-2 subtitle-1"
                  flat
                >
                {{ cols2 }}
                  {{ history.content }}
                </v-card>
              </v-col> -->
            </v-row>
          </div>
        </v-card-text>
      </v-card>
    </v-col>
  </div>
</template>

<script>
export default {
  data() {
    return{
      content: `熊本県出身のシンガーソングライター。ハイトーンの声量おばけ。
      勾玉野郎。夏が好きです。旅や神社巡り、御朱印集めが趣味。都内で活動中。`,
      histories: [
        {
          id: 1,
          year: 1994.12,
          content: '誕生。熊本生まれ。'
        },
        {
          id: 2,
          year: 2020.4,
          content: '東京在住。'
        },
      ]
    }
  },
}
</script>
