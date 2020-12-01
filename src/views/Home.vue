<template>
  <div class="home">
    <v-card
    :loading="loading"
    class="mx-auto my-12"
    max-width="384"
  >
    <template slot="progress">
      <v-progress-linear
        color="deep-purple"
        height="10"
        indeterminate
      ></v-progress-linear>
    </template>

    <v-img
      height="250"
      src="http://lorempixel.com/1000/1000/animals/3"
    ></v-img>

    <v-card-title>-Name: Wahyu Koco Permadi</v-card-title>

    <v-divider class="mx-4"></v-divider>

    <v-card-title>-NIM: 00000040112</v-card-title>

    <v-divider class="mx-4"></v-divider>

    <v-card-actions>
      <v-btn color="deep-purple lighten-2" text to="/temperature">
        Temperature
      </v-btn>
      <v-btn color="deep-purple lighten-2" text to="/weight">
        Weight
      </v-btn>
      <v-btn color="deep-purple lighten-2" text to="/time">
        Time
      </v-btn>
      <v-btn color="deep-purple lighten-2" text to="/length">
        Length
      </v-btn>
    </v-card-actions>
  </v-card>
  <v-container>
    <v-row>
      <v-col align="center">
        Made with vue.js || Vuetify
      </v-col>
    </v-row>
  </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  /*components: {
    HelloWorld
  }*/
}
</script>

<style  scoped>
  .container{
    justify-content: center;
  }
</style>
