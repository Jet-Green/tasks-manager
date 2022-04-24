<template>
  <v-container>
    <v-form>
      <v-text-field v-model="task" required></v-text-field>
      <v-btn @click="createTask">create</v-btn>
    </v-form>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  name: "Home",
  data: () => ({
    task: "",
  }),
  methods: {
    createTask: async function () {
      axios.post("http://localhost:3000/create-task", { task: this.task });
    },
  },
};
</script>

<style>
</style>