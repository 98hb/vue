<template>
  <div class="my-counter">
    <button type="button" class="btn btn-light">-</button>
    <input type="number" class="form-control inp" v-model="obj.goods_count" />
    <button type="button" class="btn btn-light">+</button>
  </div>
</template>

<script>
export default {
  props: { obj: Object },
  // 因为数量控制要通过对象"互相引用的关系"
  // 来影响外面对象里的数量值,所以最好传 对象进来
};
</script>

<style lang="less" scoped>
.my-counter {
  display: flex;
  .inp {
    width: 45px;
    text-align: center;
    margin: 0 10px;
  }
  .btn,
  .inp {
    transform: scale(0.9);
  }
}
</style>