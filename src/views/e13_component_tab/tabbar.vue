<template>
  <div class="mint-tabbar" :class="{
      'is-fixed': fixed
    }">
    <slot></slot>
  </div>
</template>

<script>
/**
 * mt-tabbar
 * @module components/tabbar
 * @desc 底部 tab，依赖 tab-item
 * @param {boolean} [fixed=false] - 固定底部
 * @param {*} value - 返回 item component 传入的 id
 *
 * @example
 * <mt-tabbar v-model="selected">
 *   <mt-tab-item id="订单">
 *     <img slot="icon" src="http://placehold.it/100x100">
 *     <span slot="label">订单</span>
 *   </mt-tab-item>
 * </mt-tabbar>
 *
 * <mt-tabbar v-model="selected" fixed>
 *   <mt-tab-item :id="['传入数组', '也是可以的']">
 *     <img slot="icon" src="http://placehold.it/100x100">
 *     <span slot="label">订单</span>
 *   </mt-tab-item>
 * </mt-tabbar>
 */
export default {
//  name: 'mt-tabbar',
  props: {
    fixed: Boolean,
    value: {}
  },
  created: function () {
    // `this` 指向 vm 实例
    console.log('tabbar is: ' + JSON.stringify(this.$props))
  }
}
</script>

<style lang="sass">
  .mint-tabbar
    background-color: #fff;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    text-align: center;
</style>
