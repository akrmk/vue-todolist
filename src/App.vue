<template>
  <div id="app">
    <form @submit.prevent="add">
      <input v-model="text">
      <button>Add</button>
    </form>
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

