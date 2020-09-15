<template>
  <div>
    <h3>子组件</h3>

    <hr />
    <Grandson />
  </div>
</template>
<script>
import Grandson from "./grandson";
export default {
  components: {
    Grandson
  },
  setup() {}
};
</script>
