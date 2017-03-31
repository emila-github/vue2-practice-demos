<script>
  export default {
    data () {
      return {
      }
    },
    components: {
    },
    props: {
      value: {
        type: Number,
        default: 100
      }
    },
    methods: {
      // Instead of updating the value directly, this
      // method is used to format and place constraints
      // on the input's value
      updateValue: function (value) {
        var formattedValue = value
          // Remove whitespace on either side
          .trim()
        // If the value was not already normalized,
        // manually override it to conform
        console.log('number-input this.$refs=', this.$refs)
        if (formattedValue !== value) {
          this.$refs.input.value = formattedValue
        }
        // Emit the number value through the input event
        this.$emit('input', Number(formattedValue))
      }
    }
  }
</script>

<template>
  <span>
    $
    <input
      ref="input"
      v-bind:value="value"
      v-on:input="updateValue($event.target.value)"
      >
      </span>
</template>

<style scoped>

</style>
