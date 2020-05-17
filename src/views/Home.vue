<template>
  <v-container class="d-flex flex-wrap mx-2 pa-2">
    <v-card height="20%" width="60%">
      <v-list three-line class="mx-auto">
        <template v-for="item in items">
          <v-list-item :key="item.title">
            <v-list-item-avatar class="profile" size="100">
              <v-img :src="item.avatar"></v-img>
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title class="title" v-html="item.title"></v-list-item-title>
              <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </template>
      </v-list>
      <v-toolbar color="white">
        <template v-slot:extension>
          <v-tabs fixed-tabs v-model="tab">
            <v-tabs-slider color="blue"></v-tabs-slider>

            <v-tab v-for="(tab1,item) in tabs" :key="item">{{ tab1 }}</v-tab>
          </v-tabs>
        </template>
      </v-toolbar>

      <v-tabs-items v-model="tab">
        <v-tab-item>
          <v-card flat>
            <v-card-text>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</v-card-text>
          </v-card>
        </v-tab-item>
        <v-tab-item>
          <Information />
          <Experience />
          <Education />
          <Skills />
        </v-tab-item>
      </v-tabs-items>
    </v-card>

    <v-col class="d-flex flex-wrap">
      <v-row>
        <Evaluation />
      </v-row>
    </v-col>
    <TeamNotes />
    <Tasks />
  </v-container>
</template>
<script>
import Information from "../components/Information";
import Experience from "../components/Experience";
import Education from "../components/Education";
import Skills from "../components/Skills";
import Evaluation from "../components/Evaluation";
import TeamNotes from "../components/TeamNotes";
import Tasks from "../components/Tasks";

export default {
  name: "Home",
  components: {
    Information,
    Experience,
    Education,
    Skills,
    Evaluation,
    TeamNotes,
    Tasks
  },
  data() {
    return {
      tab: null,
      items: [
        {
          avatar: "https://cdn.vuetifyjs.com/images/lists/1.jpg",
          title: "Kamal Pratap",
          subtitle:
            "<span class='text--primary'>Full stack developer</span><br><p>last activity</p>"
        }
      ],
      tabs: ["OVERVIEW", "ACTIVITIES", "ASSESSMENT", "FILES", "RESUME"]
    };
  }
};
</script>
