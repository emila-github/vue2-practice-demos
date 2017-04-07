<template>
  <a class="mint-tab-item"
    @click="$parent.$emit('input', id)"
    :class="{ 'is-selected': $parent.value === id }">
    <div class="mint-tab-item-icon"><slot name="icon"></slot></div>
    <div class="mint-tab-item-label"><slot></slot></div>
  </a>
</template>

<script>
/**
 * mt-tab-item
 * @module components/tab-item
 * @desc 搭配 tabbar 或 navbar 使用
 * @param {*} id - 选中后的返回值，任意类型
 * @param {slot} [icon] - icon 图标
 * @param {slot} - 文字
 *
 * @example
 * <mt-tab-item>
 *   <img slot="icon" src="http://placehold.it/100x100">
 *   订单
 * </mt-tab-item>
 */
export default {
  name: 'mt-tab-item',

  props: ['id'],
  created: function () {
    // `this` 指向 vm 实例
    console.log('tab-item is: ' + JSON.stringify(this.$props))
  },
  methods: {
  }
}
</script>

<style lang="sass" scoped>
  .mint-tab-item
    display: block;
    padding: 7px 0;
    flex: 1;
    text-decoration: none;
  .is-selected
    color: red;

</style>
