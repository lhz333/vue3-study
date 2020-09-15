<template>
  <div>
    <h2>------template refs------</h2>
    <p ref="pRefs">p标签</p>
    <button @click="getSonCount">获取子组件的count值</button>
    <hr />
    <Son ref="sonRefs" />
  </div>
</template>
<script>
import { ref, onMounted } from "@vue/composition-api";
import Son from "./refs/son";
export default {
  components: {
    Son
  },
  setup() {
    // 通过 ref() 还可以引用页面上的元素或组件

    // 创建一个 DOM 引用
    const pRefs = ref(null);
    const sonRefs = ref(null);

    // 在 DOM 首次加载完毕之后，才能获取到元素的引用
    onMounted(() => {
      console.log(pRefs.value);
      pRefs.value.style.color = "green";
    });

    // 展示子组件中 count 的值
    const getSonCount = () => {
      console.log(`获取子组件的count值:${sonRefs.value.count}`);
    };

    // 把创建的引用 return 出去
    return {
      pRefs,
      sonRefs,
      getSonCount
    };
  }
};
</script>
