/**
 *
 * @authors sean(eli01linux@aliyun.com)
 * @date    2016-11-28 17:22:21
 */
<script>
  export default {
    data () {
      return {
        parentMsg: 'init'
      }
    },
    components: {
      'child': {
        props: ['initialCounter'],
        data: function () {
          // 定义一个局部变量，并用 prop 的值初始化它
          return { counter: this.initialCounter }
        },
        template: `<div>
          <input v-model="initialCounter"></input>
          <span>{{ initialCounter }}</span>
        </div>`,
        methods: {
        }
      }
    }
  }
</script>

<template>
  <div>
    <h2>prop 作为初始值传入后，子组件想把它当作局部数据来用</h2>
    <input v-model="parentMsg">
    <br>
    子组件：<child v-bind:initial-counter="parentMsg"></child>
    <!-- <child :my-message="parentMsg"></child> -->
  </div>
</template>

<style scoped>

</style>
