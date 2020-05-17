<template>
  <v-app>
    <v-container text height="30%" width="40%">
      <v-card text class="flex flex-wrap">
        <v-toolbar flat>
          <v-toolbar-title>Evaluation</v-toolbar-title>
          <v-spacer></v-spacer>

          <v-btn x-small rounded text color="light" v-on="on">
            <v-icon>event_note</v-icon>
            <v-content class="blue--text">Schedule</v-content>
          </v-btn>
          <v-spacer></v-spacer>
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
  </v-app>
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
