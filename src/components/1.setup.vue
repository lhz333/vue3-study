<template>
  <div>------测试setup------</div>
</template>
<script>
export default {
  props: {
    msg: {
      type: String,
      default: "信息模板"
    }
  },
  beforeCreate() {
    console.log("--------------setup函数使用--------------");
    console.log("this is beforeCreate");
  },
  setup(props, context) {
    // setup函数在生命周期函数beforeCreate和created之间执行
    console.log("this is setup");
    // props是setup函数的第一个参数，是组件外部传入进来的属性，与vue2.0的props基本是一致的
    console.log(this); // undefined  setup函数中是没有this的
    console.log(props);
    console.log(context);
  },
  created() {
    console.log("this is created");
  }
};
</script>

<style lang="less" scoped></style>
