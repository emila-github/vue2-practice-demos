<script>
  import currencyInput from './e11_component_props_check/currency-input'
  import customInput from './e11_component_props_check/custom-input'
  import custom2Input from './e11_component_props_check/custom2-input'
  import numberInput from './e11_component_props_check/number-input'
  import exampleProps from './e11_component_props_check/example-props'
  export default {
    data () {
      return {
        propA: 1,
        propB: '2',
        propC: '2',
        propE: {
          a: 'a1',
          b: 'b1'
        },
        propF: 20,
        currency: 0,
        custom: 'custom',
        custom2: 'custom2',
        custom3: 'custom3',
        number: 111,
        something: 'somethinginit'
      }
    },
    components: {
      'example-props': exampleProps,
      'currency-input': currencyInput,
      'number-input': numberInput,
      'custom2-input': custom2Input,
      'custom-input': customInput
    }
  }
</script>

<template>
  <div>
    <h2>prop </h2>
    <h3>货币单控件组件</h3>
    <currency-input v-model="currency"></currency-input>[currency={{currency}}]<br/>
    <h3>普通单控件组件</h3>
    <custom-input v-model="custom"></custom-input>[custom={{custom}}]<br/>
    <h3>普通多控件组件</h3>
    <custom2-input :custom="custom"
                   @input="custom = arguments[0]"
                   v-bind:custom2="custom2"
                   v-on:input2="custom2 = arguments[0]"
                   :custom3 = "custom3"
                   @input3 = "custom3 = arguments[0]"
      ></custom2-input><br/>
    // custom， custom2 都是父子组件联动<br/>
    [custom={{custom}};]<br/>
    [custom2={{custom2}};]<br/>
    // custom3 组件内部联动<br/>
    [custom3={{custom3}};]<br/>

    <h3>数值单控件组件</h3>
    <number-input v-model="number"></number-input>[custom={{number}}]<br/>
    <!-- <child :my-message="parentMsg"></child> -->

    <h3>#Prop-验证</h3>
    <h4>我们可以为组件的 props 指定验证规格。如果传入的数据不符合规格，Vue 会发出警告。当组件给其他人使用时，这很有用。</h4>
    <example-props
      :propA = "propA"
      :propB = "propB"
      :propC = "propC"
      :propE = "propE"
      :propF = "propF"
      ></example-props>


  </div>
</template>

<style scoped>

</style>
