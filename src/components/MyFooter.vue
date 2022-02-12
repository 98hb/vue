<template>
  <!-- 底部 -->
  <div class="my-footer">
    <!-- 全选 -->
    <div class="custom-control custom-checkbox">
      <input
        type="checkbox"
        class="custom-control-input"
        id="footerCheck"
        v-model="isAll"
      />
      <label class="custom-control-label" for="footerCheck">全选</label>
    </div>
    <!-- 合计 -->
    <div>
      <span>合计:</span>
      <span class="price">¥ 0</span>
    </div>
    <!-- 按钮 -->
    <button type="button" class="footer-btn btn btn-primary">结算 ( 0 )</button>
  </div>
</template>

<script>
// 目标: 全选
// 1. v-model关联全选 - 复选框(v-model后变量计算属性)
// 2. 页面(视图层)v(true)-> 数据层(变量-) 计算属性(完整写法)
// 3. 把true/false同步给所有小选框选中状态上
// 小选 -> 全选
// App.vue里list数组 - > MyFooter.vue
// isAll的get方法里,统计状态影响全选框
export default {
  props: {
    arr: Array,
  },
  computed: {
    isAll: {
      set(val) {
        //val 就是关联表单的值(true/false)
        // console.log(val);
        this.$emit("changeAll", val);
      },
      get() {
        // 查找小选框关联的属性有没有不符合勾选的条件
        // 直接原地false
        return this.arr.every((obj) => obj.goods_state === true);
      },
    },
  },
};
</script>

<style lang="less" scoped>
.my-footer {
  position: fixed;
  z-index: 2;
  bottom: 0;
  width: 100%;
  height: 50px;
  border-top: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 10px;
  background: #fff;

  .price {
    color: red;
    font-weight: bold;
    font-size: 15px;
  }
  .footer-btn {
    min-width: 80px;
    height: 30px;
    line-height: 30px;
    border-radius: 25px;
    padding: 0;
  }
}
</style>