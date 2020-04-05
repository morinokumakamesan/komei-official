<template>
  <v-row>
    <v-col cols="12" sm="6" offset-sm="3">
      <v-card flat>
        <v-container fluid>
          <v-row>
            <v-col
              v-for="(photo, i) in photos"
              :key="i"
              class="d-flex child-flex"
              cols="4"
            >
              <v-card flat tile class="d-flex">
                <v-img
                  :src="photo.src"
                  aspect-ratio="1"
                  class="grey lighten-2"
                >
                  <template v-slot:placeholder>
                    <v-row
                      class="fill-height ma-0"
                      align="center"
                      justify="center"
                    >
                      <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                    </v-row>
                  </template>
                </v-img>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return{
      photos: [
        {
          id:1,
          src: require('../assets/images/1.jpg'),
        },
        {
          id:2,
          src: require('../assets/images/2.jpg'),
        },
        {
          id:3,
          src: require('../assets/images/3.jpg'),
        },
        {
          id:4,
          src: require('../assets/images/4.jpg'),
        },
        {
          id:5,
          src: require('../assets/images/5.jpg'),
        },
        {
          id:6,
          src: require('../assets/images/6.jpg'),
        },
        {
          id:7,
          src: require('../assets/images/7.jpg'),
        },
        {
          id:8,
          src: require('../assets/images/8.jpg'),
        },
        {
          id:9,
          src: require('../assets/images/9.jpg'),
        },
      ]
    }
  }
}
</script>