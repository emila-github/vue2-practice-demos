/**
 * 
 * @authors sean(eli01linux@aliyun.com)
 * @date    2016-11-28 15:33:29
 */
<script>
  export default {
    data () {
      return {
        numbers: [ 1, 2, 3, 4, 5 ]
      }
    },
    methods: {
      even: function (numbers) {
        return numbers.filter(function (number) {
          return number % 2 === 0
        })
      }
    }
  }
</script>

<template>
  <div>
    <ul>
      <li v-for="n in even(numbers)">{{ n }}</li>
    </ul>  
  </div>
</template>

<style scoped>
  
</style>
