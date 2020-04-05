<template style="background-color: #898989">
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
    <!-- <mainProfile class="animate"/> -->
    <mainNews class="animate"/>
    <mainLive class="animate"/>
  </v-layout>
</template>

<script>
// import mainProfile from '~/components/mainProfile.vue'
import mainNews from '~/components/mainNews.vue'
import mainLive from '~/components/mainLive.vue'

export default {
  components: {
    // mainProfile,
    mainNews,
    mainLive,
  },
  data() {
    return {
      title: '杉本孔明',
      img_main: require('../assets/images/main.jpg')
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
  }
}
</script>
