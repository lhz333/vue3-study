<template>
  <div>
    <h2>------ref函数------</h2>
    <p>{{ count }}</p>
    <button @click="count += 1">+1</button>
    <p>{{ name }}</p>
  </div>
</template>

<script>
import { isRef, ref, reactive } from "@vue/composition-api";
export default {
  data() {
    return {};
  },
  setup() {
    console.log("--------------ref--------------");
    // ref函数用来根据给定的值创建一个响应式的数据对象，ref()函数调用的返回值是一个对象，这个对象上只包含一个.value属性

    // 创建响应式数据对象，初始值为0
    const count = ref(0);

    // 如果要访问ref()创建出的响应式数据对象，需要通过.value属性
    console.log(count.value);
    count.value++;
    console.log(count.value);

    // 可以把ref函数创建出的数据对象 挂载到reactive函数上
    const name = ref("测试");

    const state = reactive({
      name
    });
    // 新的ref会覆盖旧的ref
    const newName = ref("新测试");
    state.name = newName;

    // isRef()用来判断某个值是否为ref()创建出来的对象；
    console.log(isRef(name));
    console.log(isRef(state));

    return { ...state, count };
  }
};
</script>
