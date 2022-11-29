<template>
  <table class="my-table">
    <thead>
      <tr>
        <slot name="th"></slot>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(item, index) in goods" :key="item.id">
        <slot name="tb" :item="item" :index="index"> </slot>
      </tr>
    </tbody>
  </table>
</template>

<script>
// import myTag from "./myTag.vue";
export default {
  props: {
    goods: Array,
  },
  //   components: {
  //     myTag,
  //   },
};
</script>

<style lang="less" scoped>
img {
  width: 100px;
  height: 100px;
  object-fit: contain;
  vertical-align: middle;
}
.my-table {
  width: 100%;
  border-spacing: 0;
  img {
    width: 100px;
    height: 100px;
    object-fit: contain;
    vertical-align: middle;
  }
  th {
    background: #f5f5f5;
    border-bottom: 2px solid #069;
  }
  td {
    border-bottom: 1px dashed #ccc;
  }
  td,
  th {
    text-align: center;
    padding: 10px;
    transition: all 0.5s;
    &.red {
      color: red;
    }
  }
  .none {
    height: 100px;
    line-height: 100px;
    color: #999;
  }
}

.my-tag {
  cursor: pointer;
  .input {
    appearance: none;
    outline: none;
    border: 1px solid #ccc;
    width: 100px;
    height: 40px;
    box-sizing: border-box;
    padding: 10px;
    color: #666;
    &::placeholder {
      color: #666;
    }
  }
}
</style>