<script>
  export default {
    data () {
      return {}
    },
    components: {
      'todo-item': {
        template: '<li>This is a todo</li>'
      }
    }
  }
</script>

<template>
  <ol>
    <!-- Create an instance of the todo-item component -->
    <todo-item></todo-item>
  </ol>
</template>

<style lang="sass">

</style>
