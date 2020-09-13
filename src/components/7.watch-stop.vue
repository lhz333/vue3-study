<template>
  <div>
    <h2>------watch stop------</h2>
    <p>count的值：{{ count }}</p>
    <button @click="stopWatch">停止监听</button>
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

    var timer = setInterval(() => {
      count.value += 1;
    }, 2000);

    // 停止监听的同时 清除定时器
    const stopWatch = () => {
      clearInterval(timer);
      stop();
    };

    return {
      count,
      stop,
      stopWatch
    };
  }
};
</script>
