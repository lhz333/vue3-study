<template>
  <div>
    <h2>------provide inject------</h2>

    <h1>父组件</h1>

    <template v-for="(item, index) in colorList">
      <button :key="index" @click="changeColor(item.value)">
        {{ item.name }}
      </button>
    </template>

    <hr />

    <Son />
  </div>
</template>
<script>
import { ref, reactive, provide, toRefs } from "@vue/composition-api";
import Son from "./com/son";
export default {
  components: {
    Son
  },
  setup() {
    let state = reactive({
      colorList: [
        {
          value: "red",
          name: "红色"
        },
        {
          value: "yellow",
          name: "黄色"
        },
        {
          value: "blue",
          name: "蓝色"
        }
      ]
    });

    const color = ref("red");

    let changeColor = value => {
      color.value = value;
    };

    // 父级组件中使用 provide() 函数向下传递数据
    // provide('要共享的数据名称', 被共享的数据)
    provide("color", color);

    return {
      ...toRefs(state),
      changeColor
    };
  }
};
</script>

<style lang="less" scoped></style>
