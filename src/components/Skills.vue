<template>
  <v-container fluid class="mr-2">
    <v-card class="ma-2 pa-2">
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
                <v-form class="px-3">
                  <v-text-field label="Name" v-model="name" prepend-icon="folder"></v-text-field>
                </v-form>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="blue darken-1" text @click="dialog = false">Close</v-btn>
                <v-btn color="blue darken-1" text @click="submit">Save</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-toolbar-title>
      </v-toolbar>
      <v-chip class="ma-2" app v-for="(chip,index) in chips" :key="index">
        <span>
          {{chip.name}}
          <v-icon @click="delElem(index)">cancel</v-icon>
        </span>
      </v-chip>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      name: "",
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
    delElem(index) {
      this.chips.splice(index, 1);
    },
    submit() {
      this.chips.push({ name: this.name });
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