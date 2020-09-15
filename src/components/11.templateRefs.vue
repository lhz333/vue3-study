<template>
  <div>
    <h2>------template refs------</h2>
    <p ref="pRefs">p标签</p>

    <hr />
  </div>
</template>
<script>
import { ref, onMounted } from "@vue/composition-api";
export default {
  setup() {
    // 通过 ref() 还可以引用页面上的元素或组件

    // 创建一个 DOM 引用
    const pRefs = ref(null);

    // 在 DOM 首次加载完毕之后，才能获取到元素的引用
    onMounted(() => {
      console.log(pRefs.value);
      pRefs.value.style.color = "green";
    });

    // 把创建的引用 return 出去
    return {
      pRefs
    };
  }
};
</script>
