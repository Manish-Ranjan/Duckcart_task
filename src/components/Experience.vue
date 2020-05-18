<template>
  <v-container fluid>
    <v-card>
      <v-toolbar flat>
        <v-toolbar-title>Experience</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-title>
          <v-dialog v-model="dialog" persistent max-width="400px">
            <template v-slot:activator="{ on }">
              <v-btn text color="light" v-on="on">
                <v-icon>add_circle_outline</v-icon>
              </v-btn>
            </template>
            <v-card>
              <v-card-title>
                <span class="headline">Experience</span>
              </v-card-title>
              <v-card-text>
                <v-container>
                  <v-row>
                    <v-col cols="12">
                      <v-text-field label="Title" v-model="title"></v-text-field>
                    </v-col>
                    <v-col cols="12">
                      <v-text-field label="Company" v-model="company"></v-text-field>
                    </v-col>
                    <v-col cols="12">
                      <v-text-field type="date" label="Year" v-model="year"></v-text-field>
                    </v-col>
                    <v-col cols="12">
                      <v-text-field type="text" label="Description" v-model="description"></v-text-field>
                    </v-col>
                  </v-row>
                </v-container>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="blue darken-1" text @click="dialog = false">Close</v-btn>
                <v-btn color="blue darken-1" text @click="addElem">Save</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-toolbar-title>
      </v-toolbar>
      <v-card class="pa-2" text v-for="(data,index) in academy" :key="index">
        <v-list-item-content>
          <v-list-item-title class="text--primary" v-text="data.title"></v-list-item-title>
          <v-list-item-subtitle>{{data.company}}</v-list-item-subtitle>
          <v-list-item-subtitle>{{data.year}}</v-list-item-subtitle>
          <p>{{data.description}}</p>
        </v-list-item-content>
      </v-card>
    </v-card>
  </v-container>
</template>
<script>
export default {
  data: () => ({
    dialog: false,
    academy: [
      {
        title: "Lead Designer",
        company: "Google.Inc",
        year: "sep 2019-dec 2019",
        description:
          "During my internship i develop UI and UX for an android add called Google Keep.I completely redesigned the application"
      }
    ],
    title: "",
    company: "",
    year: "",
    description: ""
  }),
  methods: {
    addElem() {
      this.academy.push({
        title: this.title,
        company: this.company,
        year: this.year,
        description: this.description
      });
    }
  }
};
</script>
