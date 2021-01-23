<template>
  <div class="team">
    <v-container>
      <h1 class="grey--text">Team</h1>
      <v-row>
        <v-col v-for="(person, i) in team" :key="i" cols="12" sm="12" md="6" lg="4" xl="3">
          <v-card flat outlined color="blue-grey lighten-5" class="text-center">
            <v-responsive class="pt-2">
              <v-avatar color="indigo" size="100">
                <v-img :src="`/avatar/${person.avatar}`" :alt="person.name"></v-img>
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <h2 class="grey--text text--darken-1 font-weight-bold">{{ person.name }}</h2>
              <p class="mt-2">{{ person.role }}</p>
            </v-card-text>
            <v-action>
              <v-btn le color="blue-grey lighten-5" depressed class>
                <v-icon left>message</v-icon>
                <span class="font-weight-regular">Message</span>
              </v-btn>
            </v-action>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      team: [
        {
          name: "Muhamad Ihsan Ansory",
          role: "Fullstack Developer",
          avatar: "1.JPG",
        },
        { name: "Lutfi Azid", role: "Designer", avatar: "2.JPG" },
        { name: "Jaka Pamungkas", role: "Content Writer", avatar: "3.JPG" },
        { name: "Fauzan Nurhikmah", role: "Game Developer", avatar: "4.JPG" },
        { name: "Riki Agustian", role: "Network Engineer", avatar: "5.JPG" },
      ],
    };
  },
};
</script>

<style>
</style>