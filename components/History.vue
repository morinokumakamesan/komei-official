<template>
  <div class="VueToNuxtLogo">
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
              History
            </v-card-title>
          </div>
          <!-- 画面サイズms以上時 -->
          <div class="hidden-sm-and-down">
            <v-card-title class="display-1 font-weight-thin" style="padding:5px 16px 5px">
              History
            </v-card-title>
          </div>
        </v-layout>
        <v-card-text style="padding:0px 16px 0px; white-space:pre-line; word-wrap:break-word;">
          <hr size="3" class="mb-3">
          <!-- 画面サイズms以上時 -->
          <div
            v-for="(history, i) in histories"
            :key="i"
            class="hidden-sm-and-down"
          >
            <v-row
              class="subtitle-1"
            >
              <v-col
                v-for="n in 2"
                :key="n"
                :cols="n === 1 ? 2 : 10"
                style="padding: 0px 5px 5px 12px;"
              >
                <v-card
                  flat
                  style="padding:5px 0px 10px"
                >
                  {{ n === 1 ? history.year : history.content }}
                </v-card>
              </v-col>
            </v-row>
          </div>

          <!-- 画面サイズms以下時 -->
          <div
            v-for="(history, i) in histories"
            :key="`history-${i}`"
            class="hidden-md-and-up"
          >
            <v-row
              class="subtitle-1"
            >
              <v-col
                v-for="n in 2"
                :key="n"
                :cols="n === 1 ? 4 : 8"
                style="padding: 0px 5px 5px 12px;"
              >
                <v-card
                  flat
                  style="padding:5px 0px 10px"
                >
                  {{ n === 1 ? history.year : history.content }}
                </v-card>
              </v-col>
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
          year: '1994.12',
          content: `熊本県益城町生まれ。
            人見知りの激しいちびっ子。
            空手を始めるも腕立て伏せが出来ない。`
        },
        {
          id: 2,
          year: '2004',
          content: `小学4年生
            サッカーを始めるも
            練習が嫌いすぎてサボる口実を作るのに必死な日々。食パンにマヨネーズをかけて食べだす。丸くなる。`
        },
        {
          id: 3,
          year: '2007 - 2009',
          content: `中学生
            めちゃくちゃ痩せる。
            部員が1人になり廃部寸前のバレー部を復活させる。`
        },
        {
          id: 4,
          year: '2009',
          content: `中学3年時
            音楽の先生に半ば強引に合唱部に入れられ
            九州大会まで行ってしまう。`
        },
        {
          id: 5,
          year: '2010 - 2012',
          content: `高校時バレーボールの強豪校へ入学するも怪我ばかりの3年間。
            最後の試合、肩の靭帯断裂状態で緩いサーブを打って終わる。
            引退後はカラオケに入り浸る。`
        },
        {
          id: 6,
          year: '2013 - 2015',
          content: `故郷を去り、愛媛の工場へ就職。
            20歳になるとお酒に浸る日々。
            先輩に騙されてパンクバンドのボーカルを務めるも1年で抜ける。
            ふと立ち寄ったアコースティックのライブバーでのライブを観て弾き語りに興味を持つ。
            今のギター『ハミングバード』を買う。
            購入してすぐに島村楽器主催の『アコパラ』に出演。
            cover曲をやるもBmが鳴らない。`
        },
        {
          id: 7,
          year: '2016.4',
          content: `熊本地震が発生。
            路上ライブで頂いたチップや当時からお世話になっているLive BARでの復興支援ライブを中心に協力していただき義援金を熊本県へ納める。
            この頃から上京を本格的に考える。`
        },
        {
          id: 8,
          year: '2016.12',
          content: `上京する。
            オリジナル曲を今更書き出す。`
        },
        {
          id: 9,
          year: '2017.2',
          content: `東京初ライブ。
            以降都内のライブハウス、路上などを中心に活動をスタート。`
        },
        {
          id: 10,
          year: '2018.5',
          content: `『修行』として神戸、松山、北九州を巡るミニツアーを敢行。`
        },
        {
          id: 11,
          year: '2018.7',
          content: `J-waveのSpark Boxにてオリジナル曲『nostalgic summer』を秦基博氏より取り上げられる。`
        },
        {
          id: 12,
          year: '2018.10',
          content: `1st mini album 『nostalgic』をリリース。
            ※現在は廃盤`
        },
        {
          id: 13,
          year: '2018.12',
          content: `初のワンマンライブ『好きなように生きたらいいさ』開催。`
        },
        {
          id: 14,
          year: '2019.4',
          content: `難聴を理由として半年の活動休止。`
        },
        {
          id: 15,
          year: '2019.11',
          content: `下北沢.風知空知にて森良太(Brian the Sun)氏とのツーマンライブを機に活動再開。
            都内、浅草を中心に活動中。`
        }
      ]
    }
  },
}
</script>
