<template>
  <div>
    <h2>------reactive函数------</h2>
    <p>count的值为：{{ count }}</p>
    <button @click="count += 1">+ 1</button>
  </div>
</template>

<script>
import { reactive } from "@vue/composition-api";
export default {
  data() {
    return {};
  },
  setup() {
    console.log("--------------reactive 函数使用--------------");
    // 创建响应式数据对象
    const state = reactive({ count: 0 });

    // setup函数中将响应式数据return出去  便可在template中使用
    return state;
  }
};
</script>

<style></style>
