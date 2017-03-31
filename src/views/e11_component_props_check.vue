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
    <!--<currency-input v-model="currency"></currency-input>[currency={{currency}}]<br/>-->
    <!--<custom-input v-model="custom"></custom-input>[custom={{custom}}]<br/>-->
    <custom2-input @input="custom = arguments[0]" :custom="custom" v-on:input2="custom2 = arguments[0]" :custom2="custom2"></custom2-input>[custom={{custom}};custom2={{custom2}}]<br/>
    <!--<number-input v-model="number"></number-input>[custom={{number}}]<br/>-->
    <!-- <child :my-message="parentMsg"></child> -->
  </div>
</template>

<style scoped>

</style>
