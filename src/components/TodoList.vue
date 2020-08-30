<template>
  <ul>
    <li v-for="(item,i) in items" v-bind:key="i">
      {{item}}
    </li>
  </ul>
</template>

<script>
  // const items = {
  //   key: Number,
  //   text: String
  // }
  export default {
    name: 'TodoList',
    props: {
      items: []
    }
  }
</script>