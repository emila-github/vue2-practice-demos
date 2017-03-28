<script>
  export default {
    data () {
      return {
      }
    },
    components: {
      'my-row': {
        template: `
          <tr>tr 组件</tr>
        `
      }
    }
  }
</script>

<template>
  <div>
    <h1>#DOM-模版解析说明</h1>
    <table>
      <my-row>内容可能会丢失</my-row>
      <tr is="my-row">这样更符合</tr>
    </table>
  </div>
</template>
