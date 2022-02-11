<template>
  <div>
    <MyHeader background="red" title="购物车案例"></MyHeader>
    <div class="main"><MyGoods></MyGoods></div>
    <MyFooter></MyFooter>
  </div>
</template>

<script>
// 目标:  项目初始化 - 静态页面
// 1. 创建项目，下包，引入bs样式
// 2. 拆分需求组件，创建 - 分别标签+样式
// 3. App.vue上显示
import MyHeader from "./components/MyHeader.vue";
import MyGoods from "./components/MyGoods.vue";
import MyFooter from "./components/MyFooter.vue";
export default {
  components: {
    MyHeader,
    MyGoods,
    MyFooter,
  },
};
</script>

<style scoped>
.main {
  padding-top: 45px;
  padding-bottom: 50px;
}
</style>