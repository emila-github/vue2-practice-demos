<script>
  export default {
    data () {
      return {
      }
    },
    components: {
    },
    props: {
      // 基础类型检测 （`null` 意思是任何类型都可以）
      propA: Number,
      // 多种类型
      propB: [String, Number],
      // 必传且是字符串
      propC: {
        type: String,
        required: true
      },
      // 数字，有默认值
      propD: {
        type: Number,
        default: 100
      },
      // 数组／对象的默认值应当由一个工厂函数返回
      propE: {
        type: Object,
        default: function () {
          return { message: 'hello' }
        }
      },
      // 自定义验证函数
      propF: {
        validator: function (value) {
          return value > 10
        }
      }
    },
    methods: {
    }
  }
</script>

<template>
  <div>
    <p>propA: {{propA}}</p>
    <p>propB: {{propB}}</p>
    <p>propC: {{propC}}</p>
    <p>propD: {{propD}}</p>
    <p>propE: {{propE}}</p>
    <p>propF: {{propF}}</p>
  </div>
</template>

<style scoped>

</style>
