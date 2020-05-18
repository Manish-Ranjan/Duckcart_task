<template>
  <v-container fluid>
    <v-card>
      <v-toolbar flat>
        <v-toolbar-title>Information</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-title>
          <!-- Dialog box for plus button -->
          <v-dialog v-model="dialog" persistent max-width="400px">
            <template v-slot:activator="{ on }">
              <v-btn text color="light" v-on="on">
                <v-icon>add_circle_outline</v-icon>
              </v-btn>
            </template>
            <v-card>
              <v-card-title>
                <span class="headline">Informationn</span>
              </v-card-title>
              <v-card-text>
                <v-form class="px-3">
                  <v-text-field label="Title" v-model="title"></v-text-field>
                  <v-text-field label="Information" v-model="info"></v-text-field>
                </v-form>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="blue darken-1" text @click="dialog = false">Close</v-btn>
                <v-btn color="blue darken-1" text @click="addElem">Save</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
          <!-- End of  Dialog box -->
        </v-toolbar-title>
      </v-toolbar>
      <v-card text v-for="(data,index) in academy" :key="index">
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>{{data.title}}</v-list-item-title>
          </v-list-item-content>

          <v-list-item-content>
            <v-list-item-title>{{data.info}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>
      </v-card>
    </v-card>
  </v-container>
</template>
<script>
export default {
  data: () => ({
    dialog: false,
    academy: [
      { title: "email", info: "kamalpratap@xyz.com" },
      { title: "phone", info: "+91-9876543232" },
      { title: "social", info: "github.com/kamalPratap" },
      { title: "link", info: "codepen.io/kamla" }
    ],
    title: "",
    info: ""
  }),
  methods: {
    addElem() {
      this.academy.push({ title: this.title, info: this.info });
    }
  }
};
</script>
