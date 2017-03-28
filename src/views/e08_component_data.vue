<script>
  var data = {counter: 0}
  export default {
    data () {
      return {
      }
    },
    components: {
      'simple-counter': {
        template: '<button v-on:click="counter += 1">{{ counter }}</button>',
        // 技术上 data 的确是一个函数了，因此 Vue 不会警告，
        // 但是我们返回给每个组件的实例的却引用了同一个data对象
        data: function () {
          return data
        }
      }
    }
  }
</script>

<template>
  <div>
    <h1>data是一个函数。但data是一个引用类型</h1>
    <simple-counter></simple-counter>
    <simple-counter></simple-counter>
    <simple-counter></simple-counter>
  </div>
</template>
