<template>
  <v-app>
    <v-container class="ml-2">
      <v-card class="m-2" height="25%" width="50%">
        <v-toolbar flat>
          <v-toolbar-title>Skills</v-toolbar-title>
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
                  <span class="headline">Skills</span>
                </v-card-title>
                <v-card-text>
                  <v-container>
                    <v-row>
                      <v-col cols="12">
                        <v-text-field label="Name" required></v-text-field>
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
          </v-toolbar-title>
        </v-toolbar>
        <v-chip class="ma-2" app v-for="(chip,index) in chips" :key="index">
          <span>
            {{chip.name}}
            <v-icon @click="delElem(index)">delete</v-icon>
          </span>
        </v-chip>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      chips: [
        { name: "python", del: true },
        { name: "web development", del: true },
        { name: "css", del: true },
        { name: "wevdevelopment", del: true },
        { name: "python", del: true },
        { name: "css", del: true },
        { name: "react", del: true },
        { name: "javascript", del: true },
        { name: "vue.js", del: true },
        { name: "django", del: true },
        { name: "Aws", del: true }
      ],
      chip: "",
      dialog: false
    };
  },
  methods: {
    delElement(index) {
      this.chips = [...this.chips.pop(index)];
    }
  }
};
</script>

<style>
</style>
// <v-card>
//           <v-card-text>
//             <v-form class="px-3">
//               <v-text-field label="Title"></v-text-field>
//             </v-form>
//           </v-card-text>
//         </v-card>