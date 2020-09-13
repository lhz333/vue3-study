<template>
  <div>
    <h2>------watch stop------</h2>
    <p>count的值：{{ count }}</p>
    <button @click="stop">停止监听</button>
  </div>
</template>

<script>
import { ref, watch } from "@vue/composition-api";
export default {
  setup() {
    console.log("--------------watch stop--------------");
    const count = ref(0);

    // 直接调用stop()便可停止监听
    const stop = watch(count, () => console.log(count.value));

    setInterval(() => {
      count.value += 1;
    }, 2000);

    return {
      count,
      stop
    };
  }
};
</script>
