<template>
  <v-dialog persistent v-model="dialog" width="500">
    <template v-slot:activator="{ on, attrs }">
      <v-btn color="success" dark v-bind="attrs" v-on="on" small>Add a New Project</v-btn>
    </template>

    <v-card>
      <v-card-title class="headline grey lighten-2">Add a New Project</v-card-title>

      <v-card-text>
        <v-form ref="form">
          <v-text-field label="Title" v-model="title" :rules="inputRules" prepend-icon="folder"></v-text-field>
          <v-textarea label="Information" v-model="content" prepend-icon="edit" :rules="inputRules"></v-textarea>
          <v-menu v-model="menu2" :close-on-content-click="false" max-width="290">
            <template v-slot:activator="{ on, attrs }">
              <v-text-field
                :rules="dateRules"
                :value="due"
                clearable
                label="Due Date"
                readonly
                v-bind="attrs"
                v-on="on"
                @click:clear="due = null"
              ></v-text-field>
            </template>
            <v-date-picker v-model="due" @change="menu2 = false"></v-date-picker>
          </v-menu>
          <v-btn color="success" @click="submit" class="mt-4">Add Project</v-btn>
        </v-form>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
import format from "date-fns";

export default {
  data() {
    return {
      dialog: false,
      title: "",
      content: "",
      due: "",
      menu2: false,
      inputRules: [(v) => v.length >= 3 || "Minimum length is 3 characters"],
      dateRules: [(v) => v !== null || "Date is required"],
    };
  },
  methods: {
    submit() {
      if (this.$refs.form.validate()) {
        this.dialog = false;
        console.log(this.title, this.content, this.due);
      }
    },
  },
  computed: {
    // dateFormat() {
    //   return this.due ? format(this.due, "Do MMM YYYY") : "";
    // },
  },
};
</script>