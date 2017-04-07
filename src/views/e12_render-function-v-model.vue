<script>
  export default {
    data () {
      return {
        msg: 'msg'
      }
    },
    // render函数中没有与v-model相应的api - 你必须自己来实现相应的逻辑
    render: function (createElement) {
      var self = this
      return createElement('div', {
      }, [
        createElement('input', {
          domProps: {
            value: self.msg
          },
          on: {
            input: function (event) {
              self.value = event.target.value
            }
          }
        }),
        createElement('div', {
          domProps: {
            innerHTML: this.msg
          }
        })
      ])
    }
  }
</script>


