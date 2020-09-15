<template>
  <div>
    <h2>------watch------</h2>
    <p>count的值：{{ count }}</p>
    <button @click="add">add</button>
    <p>name：{{ name }}</p>
    <input type="text" v-model="name" />
  </div>
</template>

<script>
import {
  watchEffect,
  watch,
  ref,
  reactive,
  toRefs
} from "@vue/composition-api";
export default {
  setup () {
    console.log("--------------watch--------------");
    const count = ref(0);

    const add = () => (count.value += 1);

    const state = reactive({
      name: "reactive",
      sex: "女"
    });
    // watchEffect的用法与watch有所不同，watchEffect会传入一个函数，然后立即执行这个函数，对于函数里面的响应式依赖会进行监听，然后当依赖发生变化时，会重新调用传入的函数
    watchEffect(() => {
      console.log(count.value);
      console.log(state.name);
    });
    // watch除了可以监听单个值或者函数返回值之外，也可以同时监听多个数据源
    watch(
      // 这里是要监听的数据 count是ref创建的数据，() => state.name是reactive创建的数据
      [count, () => state.name],
      // newValue是新值，oldValue是旧值
      (newValue, oldValue) => {
        console.log(newValue, oldValue);
      }
    );

    // watch 可以监听一个函数的返回值
    watch(
      () => {
        return state.name + state.sex;
      },
      value => {
        // state中name或者sex发生变化时，都会进入这个函数
        console.log(`名字加姓别是：${value}`);
      }
    );
    return {
      ...toRefs(state),
      count,
      add
    };
  }
};
</script>
