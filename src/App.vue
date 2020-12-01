<template>
  <v-app>
    <v-app-bar app color="#3b3b3b" dark>
        <v-tabs align-with-title>
          <v-spacer></v-spacer>
          <v-tab to="/">Home</v-tab>
          <v-tab to="/time">Time</v-tab>
          <v-tab to="/temperature">Temperature</v-tab>
          <v-tab to="/weight">Weight</v-tab>
          <v-tab to="/length">Length</v-tab>
          <v-spacer></v-spacer>
        </v-tabs>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
