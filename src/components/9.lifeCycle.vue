<template>
  <div>
    <h2>------life cycle------</h2>
    <input type="text" v-model="count" />
  </div>
</template>
<script>
// 新版的生命周期函数，可以按需导入到组件中，且只能在 setup() 函数中使用

// 下面的列表，是 vue 2.x 的生命周期函数与新版 Composition API 之间的映射关系：
//     beforeCreate -> use setup()
//     created -> use setup()
//     beforeMount -> onBeforeMount
//     mounted -> onMounted
//     beforeUpdate -> onBeforeUpdate
//     updated -> onUpdated
//     beforeDestroy -> onBeforeUnmount
//     destroyed -> onUnmounted
//     errorCaptured -> onErrorCaptured

import {
  ref,
  onMounted,
  onBeforeMount,
  onUpdated,
  onBeforeUpdate,
  onBeforeUnmount,
  onUnmounted,
  onErrorCaptured
} from "@vue/composition-api";
export default {
  setup () {
    console.log("--------------life cycle--------------");
    const count = ref(0);

    onBeforeMount(() => {
      console.log("onBeforeMount");
    });

    onMounted(() => {
      console.log("onMounted");
    });

    onBeforeUpdate(() => {
      console.log("onBeforeUpdate");
    });

    onUpdated(() => {
      console.log("onUpdated");
    });

    onBeforeUnmount(() => {
      console.log("onBeforeUnmount");
    });

    onUnmounted(() => {
      console.log("onUnmounted");
    });

    onErrorCaptured(() => {
      console.log("onErrorCaptured");
    });

    return {
      count
    };
  }
};
</script>
