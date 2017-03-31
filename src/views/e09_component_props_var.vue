/**
 *
 * @authors sean(eli01linux@aliyun.com)
 * @date    2016-11-28 17:22:21
 */
<script>
  export default {
    data () {
      return {
        parentFlag: '',
        parentMsg: ''
      }
    },
    components: {
      'child': {
        props: ['myMessage', 'dataFlag'],
        template: `<span  :data-flag="dataFlag">{{ myMessage }}-{{ dataFlag }}</span>`
      }
    }
  }
</script>

<template>
  <div>
    <h2>动态 Prop</h2>
    <input v-model="parentMsg">
    <input v-model="parentFlag">
    <br>
    <child v-bind:my-message="parentMsg" v-bind:data-flag="parentFlag"></child>
    <!-- <child :my-message="parentMsg"></child> -->
  </div>
</template>

<style scoped>

</style>
