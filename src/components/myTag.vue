<template>
  <div class="my-tag">
    <input
      v-if="isShow"
      v-model="editText"
      ref="inp"
      @keyup.enter="editname"
      class="input"
      type="text"
      placeholder="输入标签"
    />
    <div class="text" v-else @dblclick="edit">{{ value }}</div>
  </div>
</template>

<script>
export default {
  props: {
    value: String,
  },
  data() {
    return {
      isShow: false,
      editText: "",
    };
  },
  methods: {
    //双击显示编辑修改输入框,
    edit() {
      // 显示输入框
      this.isShow = !this.isShow;
      // 文本显示在输入框上
      this.editText = this.value;
      //获得焦点
      this.$nextTick(() => this.$refs.inp.focus());
    },
    //输入框键盘弹起时
    editname() {
      this.isShow = !this.isShow;
      this.$emit("input", this.editText);
    },
  },
};
</script>

<style>
</style>