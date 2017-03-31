<script>
  export default {
    data () {
      return {
//        dcustom: this.$props.custom,
//        dcustom2: this.$props.custom2
        dcustom3: this.$props.custom3
      }
    },
    components: {
    },
    props: ['custom3', 'custom2', 'custom'],
    methods: {
      updateValue3: function (value) {
        var formattedValue = value
        console.log('updateValue3 this.$refs=', this.$refs)
        this.$refs.custom3.value = formattedValue
//        this.$emit('input3', formattedValue)
      },
      // Instead of updating the value directly, this
      // method is used to format and place constraints
      // on the input's valuehai song
      updateValue2: function (value) {
        var formattedValue = value
          // Remove whitespace on either side
          .trim()
        // If the value was not already normalized,
        // manually override it to conform
        console.log('updateValue2 this.$refs=', this.$refs)
        if (formattedValue !== value) {
          this.$refs.custom2.value = formattedValue
        }
        // Emit the number value through the input event
        this.$emit('input2', formattedValue)
      },
      updateValue: function (value) {
        var formattedValue = value
        console.log('updateValue this.$refs=', this.$refs)
        if (formattedValue !== value) {
          this.$refs.custom.value = formattedValue
        }
        // Emit the number value through the input event
        this.$emit('input', formattedValue)
      }
    }
  }
</script>

<template>
  <span>
    -
    <input
      ref="custom"
      v-bind:value="custom"
      v-on:input="updateValue($event.target.value)"
      >
    (custom={{custom}})
    -
    <input
      ref="custom2"
      v-bind:value="custom2"
      v-on:input="updateValue2($event.target.value)"
      >
    (custom2={{custom2}})
     -
    <input
      ref="custom3"
      :value = "dcustom3"
      v-on:input = "dcustom3 = $event.target.value"
      >
    (custom3={{dcustom3}})
      </span>
</template>

<style scoped>

</style>
