<script>
  import currencyInput from './e11_component_props_check/currency-input'
  import customInput from './e11_component_props_check/custom-input'
  import custom2Input from './e11_component_props_check/custom2-input'
  import numberInput from './e11_component_props_check/number-input'
  export default {
    data () {
      return {
        currency: 0,
        custom: 'custom',
        custom2: 'custom2',
        custom3: 'custom3',
        number: 111,
        something: 'somethinginit'
      }
    },
    components: {
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
  </div>
</template>

<style scoped>

</style>
