<template>
  <div>
    <h2>------toRefs------</h2>
    <p>{{ count }}</p>
    <button @click="add">+1</button>
  </div>
</template>

<script>
import { reactive, toRefs } from "@vue/composition-api";
export default {
  setup() {
    console.log("--------------toRef--------------");
    // toRefs()函数可以将reactive()创建出来的响应式对象，转换为普通对象，只不过，这个对象上的每个属性接点，都是ref()类型的响应式数据

    const state = reactive({
      count: 0
    });

    // 定义页面上的事件处理函数
    const add = () => {
      state.count += 1;
    };

    // toRefs将state上的每个属性，都转化为ref形式的响应式数据
    return { ...toRefs(state), add };
  }
};
</script>
