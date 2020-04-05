<template style="background-color: #898989">
  <v-layout
    column
    justify-center
  >
    <div class="text-center hidden-md-and-up">
      <v-img
        :src=img_profile
      >
      </v-img>
    </div>
    <v-col
      md="10"
      offset-md="1"
      class="hidden-sm-and-down"
    >
      <v-img
        :src=img_profile
      >
      </v-img>
    </v-col>
    <div>
      
    </div>
    <History class="animate"/>
  </v-layout>
</template>

<script>
import History from '~/components/History.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    History,
    VuetifyLogo
  },
  data() {
    return {
      title: '杉本孔明',
      img_profile: require('../assets/images/profile.jpg')
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