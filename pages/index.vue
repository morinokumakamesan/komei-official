<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <div class="text-center">
        <v-img
          :src=img_main
        >
        </v-img>
      </div>
      <mainNews/>
    </v-flex>
  </v-layout>
</template>

<script>
import mainNews from '~/components/mainNews.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    mainNews,
    VuetifyLogo
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
  }
}
</script>
