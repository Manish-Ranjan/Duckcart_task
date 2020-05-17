<template>
  <nav class="grey">
    <v-app-bar color="white" elevate-on-scroll scroll-target="#scrolling-techniques-7">
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-toolbar-title class="text-upercase">EMPLOYEES/PROFILE</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text color="light-grey">BACK</v-btn>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list nav dense>
        <v-list-item-group v-model="group" active-class="deep-purple--text text--accent-4">
          <v-list-item>
            <v-list-item-icon>
              <v-icon>list</v-icon>
            </v-list-item-icon>

            <v-list-item-title>INOGIT</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>dashboard</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Dashboard</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>group</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Candidates</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>work</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Jobs</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>email</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Mailbox</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>settings</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Setting</v-list-item-title>
          </v-list-item>
          <hr />

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Account</v-list-item-title>
          </v-list-item>
          <v-list-item v-for="(value,index) in navbar" :key="index">
            <v-list-item-icon>
              <v-icon>{{value.icon}}</v-icon>
            </v-list-item-icon>
            <v-list-item-title>{{value.title}}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    navbar: [
      { icon: "waves", title: "Pools" },
      { icon: "assessment", title: "Assessments" },
      { icon: "group_work", title: "Team Members" },
      { icon: "monetization_on", title: "Billing" },
      { icon: "list_alt", title: "Guidelines" },
      { icon: "feedback", title: "Feedback" },
      { icon: "contact_support", title: "Contact Us" }
    ]
  })
};
</script>