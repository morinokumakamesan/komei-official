<template>
  <!-- <v-app> -->
  <v-app light style="background: white">
    <!-- 画面サイズmd以上時のヘッダー -->
    <v-app-bar
      :clipped-left="clipped"
      color="#222222"
      fixed
      app
      class="hidden-sm-and-down"
    >
      <v-toolbar-title class="top_title" @click="goHome" v-text="title"/>
        <v-layout row justify-end>
          <v-btn 
            text
            v-for="(btn, i) in btns"
            color="white"
            :to="btn.to"
            :key="i"
            router
            exact
          >
          {{ btn.title }}
          </v-btn>
        </v-layout>
    </v-app-bar>

    <!-- 画面サイズms以下時のヘッダー -->
    <v-app-bar
      :clipped-left="clipped"
      color="#222222"
      fixed
      app
      class="hidden-md-and-up"
    >
      <v-toolbar-title class="top_title" @click="goHome" v-text="title"/>
      <v-spacer />
      <v-btn
        color="white"
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content max-width=100%>
        <nuxt />
    </v-content>

    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer
      color="#222222"
    >
      <v-layout justify-center>
        <span style="color:white">&copy; {{ new Date().getFullYear() }} 杉本孔明</span>
      </v-layout>
    </v-footer>
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
          icon: 'home',
          title: 'Top',
          to: '/'
        },
        {
          icon: 'person',
          title: 'Profile',
          to: '/profile'
        },
        {
          icon: 'label',
          title: 'News',
          to: '/news'
        },
        {
          icon: 'calendar_today',
          title: 'Schedule',
          to: '/schedule'
        },
        {
          icon: 'photo',
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
          title: 'Top',
          to: '/'
        },
        {
          title: 'Profile',
          to: '/profile'
        },
        {
          title: 'News',
          to: '/news'
        },
        {
          title: 'Schedule',
          to: '/schedule'
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
  color: white
  font-size: 22px
  font-family: 'Sawarabi Gothic', sans-serif

</style>