<template>
  <v-app>
    <v-container text class="ma-2">
      <v-card text class="ma-2 pd-2" height="10%" width="60%">
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
                  <v-container>
                    <v-row>
                      <v-col cols="12">
                        <v-text-field label="Email"></v-text-field>
                      </v-col>
                      <v-col cols="12">
                        <v-text-field label="Phone"></v-text-field>
                      </v-col>
                      <v-col cols="12">
                        <v-text-field type="text" label="Social"></v-text-field>
                      </v-col>
                      <v-col cols="12">
                        <v-text-field type="text" label="link"></v-text-field>
                      </v-col>
                    </v-row>
                  </v-container>
                </v-card-text>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn color="blue darken-1" text @click="dialog = false">Close</v-btn>
                  <v-btn color="blue darken-1" text @click="dialog = false">Save</v-btn>
                </v-card-actions>
              </v-card>
            </v-dialog>
            <!-- End of  Dialog box -->
          </v-toolbar-title>
        </v-toolbar>
        <v-card text v-for="(data,index) in academy" :key="index">
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>EMAIL</v-list-item-title>
            </v-list-item-content>
            <v-list-item-content>
              <v-list-item-title>{{data.email}}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-divider></v-divider>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>PHONE</v-list-item-title>
            </v-list-item-content>
            <v-list-item-content>
              <v-list-item-title>{{data.phone}}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-divider></v-divider>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>SOCIAL</v-list-item-title>
            </v-list-item-content>
            <v-list-item-content>
              <v-list-item-title>{{data.social}}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-divider></v-divider>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>LINK</v-list-item-title>
            </v-list-item-content>
            <v-list-item-content>
              <v-list-item-title>{{data.link}}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-divider></v-divider>
        </v-card>
      </v-card>
    </v-container>
  </v-app>
</template>
<script>
export default {
  data: () => ({
    dialog: false,
    academy: [
      {
        email: "kamalpratap@xyz.com",
        phone: "+91-9876543232",
        social: "github.com/kamalPratap",
        link: "codepen.io/kamla  "
      }
    ]
  })
};
</script>
