<template style="background-color: #000000">
  <v-layout
    column
    justify-center
  >
    <div class="text-center hidden-md-and-up">
      <v-img
        width="100%"
        height="250px"
        :src=img_schedule
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
        :src=img_schedule
        decoding="async"
      >
      </v-img>
    </v-col>
    <mainSchedule :num=100 />
  </v-layout>
</template>

<script>
import mainSchedule from '~/components/mainSchedule.vue'
export default {
  components: {
    mainSchedule,
  },
  data() {
    return {
      title: '杉本孔明',
      img_schedule: require('../assets/images/schedule.jpg')
    }
  },
}
</script>
