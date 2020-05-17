<template>
  <template>
    <nav>
      <v-app-bar flat app>
        <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        <v-spacer></v-spacer>
        <v-toolbar-title class="text-uppercase">
          <span>Employees/profiles</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn flat>BACK</v-btn>
      </v-app-bar>
      <v-navigation-drawer app v-model="drawer"></v-navigation-drawer>
    </nav>
  </template>
</template>
</template>

<script>
export default {
  name: "Check",
  data() {
    return {
      name: "",
      value: []
    };
  },
  methods: {
    addElem() {
      this.value.push(this.name);
    }
  }
};
</script>

<style>
</style>
<v-btn>
              <v-icon>add_circle_outline</v-icon>
            </v-btn>