<script>
  import child from '../components/child'
  export default {
    data () {
      return {
        groceryList: [
          { text: 'Vegetables' },
          { text: 'Cheese' },
          { text: 'Whatever else humans are supposed to eat' }
        ]
      }
    },
    components: {
      // 将子组件作为子子组件
      'child-render': {
        props: ['myMessage'],
        render: function (createElement) {
          console.log(this)
          // var myMessage = this.props['my-message']
          return createElement('div', {
            'class': {
              foo: true,
              foo1: true,
              bar: false
            }
          }, [
            createElement(child, {
              props: this.$props // 读取父级props
            })
          ])
        }
      },
      // 用render方法代替template
      // Define a new component called todo-item
      'todo-item': {
        // The todo-item component now accepts a
        // "prop", which is like a custom attribute.
        // This prop is called todo.
        props: ['todo'],
        // template: '<li>{{ todo.text }}</li>'
        render: function (createElement) {
          return createElement('li', this.todo.text)
        }
      }
    }
  }
</script>

<template>
  <div>
    <child-render my-message="hello!"></child-render>
    <ol>
      <!-- Now we provide each todo-item with the todo object    -->
      <!-- it's representing, so that its content can be dynamic -->
      <todo-item v-for="item in groceryList" v-bind:todo="item"></todo-item>
    </ol>
  </div>
</template>

<style lang="sass">

</style>
