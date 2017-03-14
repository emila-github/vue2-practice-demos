<script>
  import Vue from 'vue'
  // Define a new component called todo-item
  Vue.component('todo-item', {
    // The todo-item component now accepts a
    // "prop", which is like a custom attribute.
    // This prop is called todo.
    props: ['todo'],
    template: '<li>{{ todo.text }}</li>'
  })
  export default {
    data () {
      return {
        groceryList: [
          { text: 'Vegetables' },
          { text: 'Cheese' },
          { text: 'Whatever else humans are supposed to eat' }
        ]
      }
    }
  }
</script>

<template>
  <ol>
    <!-- Now we provide each todo-item with the todo object    -->
    <!-- it's representing, so that its content can be dynamic -->
    <todo-item v-for="item in groceryList" v-bind:todo="item"></todo-item>
  </ol>
</template>

<style lang="sass">

</style>
