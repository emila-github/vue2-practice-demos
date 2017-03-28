<script>
  export default {
    data () {
      return {
      }
    },
    components: {
      'my-component': {
        template: '<span>{{ message }}</span>',
        data: {
          message: 'hello'
        }
      }
    }
  }
</script>

<template>
  <div>
    <h1>这里是一个错误示例，data是一个对象 ，那么 Vue 会停止，并在控制台发出警告，告诉你在组件中 data 必须是一个函数。data 必须是一个函数</h1>
    <my-component></my-component>
  </div>
</template>
