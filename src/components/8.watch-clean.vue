<template>
  <div>
    <h2>------watch clean------</h2>
    <input type="text" v-model="name" />
  </div>
</template>

<script>
import { ref, watch } from "@vue/composition-api";
export default {
  setup() {
    const name = ref("");

    const asyncprint = (newVal, oldVal) => {
      return setTimeout(() => {
        console.log(newVal, oldVal);
      }, 1000);
    };

    watch(name, (newValue, oldValue, onCleanUp) => {
      const timer = asyncprint(newValue, oldValue);
      // 如果wacth监听被重复执行了，则会先清除上次未完成的异步任务
      onCleanUp(() => clearTimeout(timer));
    });

    return {
      name
    };
  }
};
</script>
