<template>
  <div class="dashboard">
    <v-container>
      <h1 class="grey--text">My Projects</h1>
      <template>
        <v-expansion-panels hover>
          <v-expansion-panel v-for="(project, i) in myProjects" :key="i">
            <v-expansion-panel-header>{{ project.title }}</v-expansion-panel-header>
            <v-expansion-panel-content class="px-3 grey--text">
              <div class="font-weight-bold">Due {{ project.due }}</div>
              <div>{{ project.content }}</div>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </template>
    </v-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Create A Mobile App",
          person: "PapandayanDev",
          due: "2 january 2020",
          status: "completed",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, iure! Voluptatum, ipsam consequuntur. Earum dolorem corporis dolore voluptatibus impedit fugit deleniti? Illo eveniet inventore eos earum, culpa accusantium id accusamus?",
        },

        {
          title: "Ecommerce Maintenance",
          person: "CikurayDev",
          due: "29 June 2020",
          status: "ongoing",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, iure! Voluptatum, ipsam consequuntur. Earum dolorem corporis dolore voluptatibus impedit fugit deleniti? Illo eveniet inventore eos earum, culpa accusantium id accusamus?",
        },
        {
          title: "Build Desktop Cashier",
          person: "GunturDev",
          due: "17 April 2020",
          status: "canceled",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, iure! Voluptatum, ipsam consequuntur. Earum dolorem corporis dolore voluptatibus impedit fugit deleniti? Illo eveniet inventore eos earum, culpa accusantium id accusamus?",
        },
        {
          title: "Make Web Chat",
          person: "HarumanDev",
          due: "1 March 2020",
          status: "ongoing",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, iure! Voluptatum, ipsam consequuntur. Earum dolorem corporis dolore voluptatibus impedit fugit deleniti? Illo eveniet inventore eos earum, culpa accusantium id accusamus?",
        },
        {
          title: "Shor A Array",
          person: "PapandayanDev",
          due: "8 June 2020",
          status: "ongoing",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, iure! Voluptatum, ipsam consequuntur. Earum dolorem corporis dolore voluptatibus impedit fugit deleniti? Illo eveniet inventore eos earum, culpa accusantium id accusamus?",
        },
      ],
    };
  },
  computed: {
    myProjects() {
      return this.projects.filter((project) => {
        return project.person === "PapandayanDev";
      });
    },
  },
};
</script>

<style>
</style>