<template>
  <div id="app">
    <form @submit.prevent="add">
      <input v-model="text">
    </form>
    <button @click="add">Add</button>
    <TodoList :items="items"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoList
  },
  data : () => ({
    text: '',
    items: []
  }),
  methods : {
    add: function() {
      this.items.push(this.text)
    }
  }
}
</script>

