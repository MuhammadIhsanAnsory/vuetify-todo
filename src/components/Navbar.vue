<template>
  <nav>
    <v-toolbar dark color="indigo darken-4">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-uppercase">
        <span class="font-weight-light">papandayan</span>
        <span class="font-weight-medium">dev</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>

      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn depressed color="indigo darken-4" dark v-bind="attrs" v-on="on">
            <v-icon left>expand_more</v-icon>
            <span>Menu</span>
          </v-btn>
        </template>
        <v-list>
          <v-list-item v-for="(link,i) in links" :key="i" router :to="link.route">
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn text>
        <span>sign out</span>
        <v-icon right>exit_to_app</v-icon>
      </v-btn>
    </v-toolbar>

    <v-navigation-drawer color="grey lighten-5" app v-model="drawer">
      <v-list-item>
        <v-list-item-avatar size="40">
          <v-img src="/avatar/1.JPG"></v-img>
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title class="title">PapandayanDev</v-list-item-title>
          <v-list-item-subtitle>Admin</v-list-item-subtitle>
          <Dialog />
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>
      <v-list nav v-for="(link, i) in links" :key="i">
        <v-list-item link :to="link.route">
          <v-list-item-icon>
            <v-icon>{{ link.icon }}</v-icon>
          </v-list-item-icon>
          {{ link.text }}
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
import Dialog from "./Dialog";

export default {
  components: {
    Dialog,
  },
  data() {
    return {
      drawer: false,
      links: [
        {
          icon: "dashboard",
          text: "Dashboard",
          route: "/",
        },
        {
          icon: "folder",
          text: "My Projects",
          route: "/projects",
        },
        {
          icon: "person",
          text: "Team",
          route: "/team",
        },
      ],
    };
  },
};
</script>
