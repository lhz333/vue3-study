<template>
  <div>
    <h2>------computed------</h2>
    <p>count的值：{{ count }}</p>
    <p>计算属性加1的值：{{ addValue }}</p>
    <p>计算属性减1的值：{{ reduceValue }}</p>
    <p>plusOne: {{ plusOne }}</p>
    <button @click="add">+1</button>
    <button @click="reduce">-1</button>
  </div>
</template>

<script>
import { computed, ref } from "@vue/composition-api";
export default {
  setup() {
    const count = ref(0);
    // 只读的计算属性
    const addValue = computed(() => count.value + 1);
    const reduceValue = computed(() => count.value - 1);

    // 可读可写的计算属性
    const plusOne = computed({
      get: () => count.value * 2,
      set: value => (count.value = value / 2)
    });
    const add = () => {
      count.value += 1;
    };
    const reduce = () => {
      count.value -= 1;
    };
    // 对计算属性赋值，触发set函数，count的值也会相应更新
    plusOne.value = 6;
    console.log(plusOne.value);
    console.log(count.value);
    return { count, addValue, reduceValue, add, reduce, plusOne };
  }
};
</script>
