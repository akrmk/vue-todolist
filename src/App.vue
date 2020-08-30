<template>
  <v-app>
    <div id="app">
      <v-container>
        <v-form @submit.prevent="add">
          <v-row>
            <v-text-field solo v-model="text"></v-text-field>
            <v-btn type="submit" class="mx-2" fab dark color="indigo">
              ＋
            </v-btn>
          </v-row>
        </v-form>
        <v-row>
          <v-col class="mx-5">
            <TodoList :items="items" />
          </v-col>
        </v-row>
      </v-container>
    </div>
  </v-app>
</template>

<script>
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: {
    TodoList,
  },
  data: () => ({
    text: "",
    items: [],
  }),
  methods: {
    add: function() {
      this.items.push(this.text);
      this.text = "";
    },
  },
};
</script>
