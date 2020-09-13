<template>
  <div>
    <h2>------watch------</h2>
    <p>count的值：{{ count }}</p>
    <button @click="add">add</button>
    <p>name：{{ name }}</p>
    <input type="text" @blur="changeInput" />
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
  setup() {
    console.log("--------------watch--------------");
    const count = ref(0);

    const add = () => (count.value += 1);

    const state = reactive({
      name: "reactive"
    });
    const changeInput = e => {
      state.name = e.target.value;
    };
    // watchEffect() 监听props
    watchEffect(() => {
      console.log(count.value);
      console.log(state.name);
    });
    // watch监听器
    watch(
      // 这里是要监听的数据 count是ref创建的数据，() => state.name是reactive创建的数据
      [count, () => state.name],
      // newValue是新值，oldValue是旧值
      (newValue, oldValue) => {
        console.log(newValue, oldValue);
      }
    );
    return {
      ...toRefs(state),
      count,
      add,
      changeInput
    };
  }
};
</script>
