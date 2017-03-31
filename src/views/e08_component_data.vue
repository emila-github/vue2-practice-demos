<script>
  export default {
    data () {
      return {
      }
    },
    components: {
      'simple-counter': {
        template: '<button v-on:click="counter += 1">{{ counter }}</button>',
        data: function () {
          return {counter: 0}
        }
      }
    }
  }
</script>

<template>
  <div>
    <h1>data是一个函数。但data不是一个引用类型</h1>
    <simple-counter></simple-counter>
    <simple-counter></simple-counter>
    <simple-counter></simple-counter>
  </div>
</template>
