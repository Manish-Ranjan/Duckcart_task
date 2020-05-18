<template>
  <v-container fluid class="ml-3 pa-1">
    <v-card class="ma-2 pa-2">
      <v-toolbar flat>
        <v-toolbar-title>Education</v-toolbar-title>
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
                <span class="headline">Education</span>
              </v-card-title>
              <v-card-text>
                <v-container>
                  <v-row>
                    <v-col cols="12">
                      <v-text-field label="Board" v-model="board" required></v-text-field>
                    </v-col>
                    <v-col cols="12">
                      <v-text-field label="School/college" v-model="college" required></v-text-field>
                    </v-col>
                    <v-col cols="12">
                      <v-text-field type="date" label="Year" v-model="year" required></v-text-field>
                    </v-col>
                    <v-col cols="12">
                      <v-text-field
                        type="number"
                        v-model="percentage"
                        min="1"
                        max="100"
                        label="Percentage"
                        required
                      ></v-text-field>
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
      <v-card class="ma-2" v-for="(data,index) in academy" :key="index">
        <h3 class="ma-2">{{data.board}}</h3>
        <p class="ma-2">{{data.college}}</p>
        <p class="ma-2">{{data.year}}</p>
        <p class="ma-2">Percentage: {{data.percentage}}</p>
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
        board: "SSC",
        college: "St.Mary High School",
        year: "sep 2016",
        percentage: "9.2"
      },
      {
        board: "Higher Secondary",
        college: "St.Mary High School",
        year: "sep 2016",
        percentage: "96.5"
      }
    ],
    board: "",
    college: "",
    year: "",
    percentage: ""
  }),
  methods: {
    addElem() {
      this.academy.push({
        board: this.board,
        college: this.college,
        year: this.year,
        percentage: this.percentage
      });
    }
  }
};
</script>
