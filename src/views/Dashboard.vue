<template>
  <div class="projects">
    <v-container class>
      <h1 class="grey--text">Dashboard</h1>
      <v-row class="my-3 ml-3">
        <v-tooltip bottom>
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              v-bind="attrs"
              v-on="on"
              small
              depressed
              color="white"
              class="grey--text text-lowercase"
              @click="sortBy('title')"
            >
              <v-icon left>folder</v-icon>By project name
            </v-btn>
          </template>
          <span>Sort by project name</span>
        </v-tooltip>

        <v-tooltip bottom>
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              v-on="on"
              v-bind="attrs"
              small
              depressed
              color="white ml-3"
              class="grey--text text-lowercase"
              @click="sortBy('person')"
            >
              <v-icon left>person</v-icon>By person
            </v-btn>
          </template>
          <span>Sort by person</span>
        </v-tooltip>
      </v-row>
      <v-card
        flat
        v-for="(project, i) in projects"
        :key="i"
        :class="`my-4 pa-2 project ${project.status}`"
      >
        <v-row no-gutters>
          <v-col cols="12" xs="12" sm="12" md="6">
            <div class="text-caption grey--text">Project Title</div>
            <div>{{ project.title }}</div>
          </v-col>
          <v-col cols="12" xs="6" sm="4" md="2">
            <div class="text-caption grey--text">Person</div>
            <div>{{ project.person }}</div>
          </v-col>
          <v-col cols="12" xs="6" sm="4" md="2">
            <div class="text-caption grey--text">Due By</div>
            <div>{{ project.due }}</div>
          </v-col>
          <v-col cols="12" xs="4" sm="4" md="2">
            <div class="text-caption grey--text">Status</div>
            <v-chip
              v-if="project.status == 'completed'"
              small
              text-color="white"
              color="blue"
            >{{ project.status }}</v-chip>
            <v-chip
              v-if="project.status == 'ongoing'"
              small
              text-color="white"
              color="green"
            >{{ project.status }}</v-chip>
            <v-chip
              v-if="project.status == 'canceled'"
              small
              text-color="white"
              color="red"
            >{{ project.status }}</v-chip>
          </v-col>
        </v-row>
        <v-divider></v-divider>
      </v-card>
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
      ],
    };
  },
  methods: {
    sortBy(props) {
      this.projects.sort((a, b) => (a[props] < b[props] ? -1 : 1));
    },
  },
};
</script>

<style scoped>
.project.completed {
  border-left: 4px solid rgb(57, 84, 238);
}
.project.ongoing {
  border-left: 4px solid rgb(72, 238, 57);
}
.project.canceled {
  border-left: 4px solid rgb(252, 44, 44);
}
</style>