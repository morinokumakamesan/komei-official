<template>
  <v-app>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      img_main: require('../assets/images/main.jpg'),
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'person',
          title: 'Profile',
          to: '/profile'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'News',
          to: '/news'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Photos',
          to: '/photos'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: '杉本 孔明',
      btns: [
        {
          title: 'Profile',
          to: '/profile'
        },
        {
          title: 'News',
          to: '/news'
        },
        {
          title: 'Photos',
          to: '/photos'
        },
      ],
    }
  },
  methods: {
    goHome() {
      this.$router.push('/')
    },
  }
}
</script>
<style lang="sass">
.top_title 
  cursor: pointer
  color: black
  font-weight: bold
  font-size: 22px
  font-family: 'Sawarabi Gothic', sans-serif

</style>