<script>
  import mtTabbar from './e13_component_tab/tabbar'
  import mtTabItem from './e13_component_tab/tab-item'
  export default {
    data () {
      return {
        selected: '3'
      }
    },
    components: {
      'mt-tabbar': mtTabbar,
      'mt-tab-item': mtTabItem
    }
  }
</script>

<template>
  <div>
    <h2>tabbar </h2>

    <mt-tabbar class="page-part" v-model="selected">
      <mt-tab-item id="1">选项一</mt-tab-item>
      <mt-tab-item id="2">选项二</mt-tab-item>
      <mt-tab-item id="3">选项三</mt-tab-item>
    </mt-tabbar>
    {{selected}}

  </div>
</template>

<style scoped>

</style>
