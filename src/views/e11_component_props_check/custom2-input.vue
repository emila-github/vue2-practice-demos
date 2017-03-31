<script>
  export default {
    data () {
      return {
//        dcustom: this.$props.custom,
//        dcustom2: this.$props.custom2
      }
    },
    components: {
    },
    props: ['custom2', 'custom'],
    methods: {
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
      </span>
</template>

<style scoped>

</style>
