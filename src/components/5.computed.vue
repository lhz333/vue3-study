<template>
  <div>
    <h2>------computed------</h2>
    <p>count的值：{{ count }}</p>
    <p>计算属性的值：{{ newValue }}</p>
    <button @click="add">+1</button>
    <button @click="reduce">-1</button>
  </div>
</template>

<script>
import { computed, ref } from "@vue/composition-api";
export default {
  setup() {
    const count = ref(0);
    const newValue = computed(() => count.value + 1);
    const add = () => {
      count.value += 1;
    };
    const reduce = () => {
      count.value -= 1;
    };
    return { count, newValue, add, reduce };
  }
};
</script>
