<template>
  <v-app class="grey lighten-4">
    <Navbar />
    <v-content>
      <!-- Provides the application the proper gutter -->
      <v-container fluid>
        <!-- If using vue-router -->
        <router-view></router-view>
      </v-container>
    </v-content>
  </v-app>
</template>
<script>
import Navbar from "../src/components/Navbar";

export default {
  name: "App",
  components: { Navbar },
  data() {
    return {};
  }
};
</script>
<style scoped>
</style>