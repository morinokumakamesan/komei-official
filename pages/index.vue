<template>
  <v-layout
    column
    justify-center
  >
    <div class="text-center hidden-md-and-up">
      <v-img
        width="100%"
        height="250px"
        :src=img_main
        decoding="async"
      >
      </v-img>
    </div>
    <v-col
      md="10"
      offset-md="1"
      class="hidden-sm-and-down"
    >
      <v-img
        width="100%"
        height="700px"
        :src=img_main
        decoding="async"
      >
      </v-img>
    </v-col>
    <mainNews :bg_color=grey :num=5 />
    <v-lazy
        :options="{
          threshold: .5
        }"
        transition="fade-transition"
      >
      <mainSchedule :today="today" :num=5 />
    </v-lazy>
    <!-- <mainProfile class="animate"/> -->
    <v-lazy
        :options="{
          threshold: .5
        }"
        transition="fade-transition"
      >
      <twitter/>
    </v-lazy>
  </v-layout>
</template>

<script>
import mainNews from '~/components/mainNews.vue'
import mainSchedule from '~/components/mainSchedule.vue'
import mainProfile from '~/components/mainProfile.vue'
import twitter from '~/components/Twitter.vue'

export default {
  components: {
    mainNews,
    mainSchedule,
    mainProfile,
    twitter,
  },
  data() {
    return {
      title: '杉本孔明',
      img_main: require('../assets/images/main.jpg'),
      today: [],
      grey: '#F5F5F5',
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
  //   window.sr = ScrollReveal();
  //   sr.reveal('.animate');
    let tmp = new Date();
    this.today = [tmp.getMonth()+1, tmp.getDate()]
  }
}
</script>
