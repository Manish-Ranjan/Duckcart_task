<template>
  <v-container fluid class="ma-2 pa-4">
    <v-card class="ma-2 pa-4">
      <v-toolbar>
        <v-toolbar-title>Evaluation</v-toolbar-title>
        <v-spacer></v-spacer>

        <v-btn x-small rounded text color="light" v-on="on">
          <v-icon>event_note</v-icon>
          <v-content class="blue--text">Schedule</v-content>
        </v-btn>

        <v-btn x-small rounded text color="light" v-on="on">
          <v-icon>share</v-icon>
        </v-btn>
        <v-btn x-small rounded text color="light" v-on="on">
          <v-icon>near_me</v-icon>
        </v-btn>
        <v-btn x-small rounded text color="light" v-on="on">
          <v-content class="blue--text">More</v-content>
        </v-btn>
      </v-toolbar>
      <v-divider></v-divider>
      <v-toolbar flat v-for="(value,index) in toolbar" :key="index">
        <v-toolbar-title>{{value.name}}</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn small rounded text color="light" v-on="on">
          <v-icon>done</v-icon>
          <v-content class="blue--text">Proceed</v-content>
        </v-btn>
        <div v-for="(icon,index) in value.icons" :key="index">
          <v-btn small rounded text color="light" v-on="on">
            <v-icon>{{icon}}</v-icon>
          </v-btn>
        </div>
      </v-toolbar>
    </v-card>
  </v-container>
</template>
<script>
export default {
  data: () => ({
    toolbar: [
      { name: "Job Name", icons: ["not_interested", "more_horiz"] },
      { name: "Pool Name", icons: ["not_interested", "more_horiz"] }
    ]
  })
};
</script>
