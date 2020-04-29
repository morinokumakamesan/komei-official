<template>
  <v-layout
    column
    justify-center
  >
    <div class="text-center hidden-md-and-up">
      <v-img
        :src=img_main
      >
      </v-img>
    </div>
    <v-col
      md="10"
      offset-md="1"
      class="hidden-sm-and-down"
    >
      <v-img
        :src=img_main
      >
      </v-img>
    </v-col>
    <mainNews :num=5 class="animate"/>
    <mainSchedule :today="today" :num=5 class="animate"/>
    <twitter class="animate"/>
  </v-layout>
</template>

<script>
import mainNews from '~/components/mainNews.vue'
import mainSchedule from '~/components/mainSchedule.vue'
import twitter from '~/components/Twitter.vue'

export default {
  components: {
    mainNews,
    mainSchedule,
    twitter,
  },
  data() {
    return {
      title: '杉本孔明',
      img_main: require('../assets/images/main.jpg'),
      today: [],
    }
  },
  head () {
    return {
      title: this.title,
      meta: [
        // `hid` は一意の識別子として使用されます。 `vmid` は動作しないので使わないでください。
        { hid: 'description', name: 'description', content: 'My custom description' }
      ]
    }
  },
  mounted() {
    window.sr = ScrollReveal();
    sr.reveal('.animate');
    let tmp = new Date();
    this.today = [tmp.getMonth()+1, tmp.getDate()]
    console.log(this.today);
  }
}
</script>
