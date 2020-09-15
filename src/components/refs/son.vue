<template>
  <div>
    <h3>子组件</h3>

    <p>count的值是：{{ count }}</p>
    <button @click="count += 1">+1</button>
  </div>
</template>
<script>
import { ref } from "@vue/composition-api";
export default {
  setup() {
    const count = ref(0);

    return {
      count
    };
  }
};
</script>
