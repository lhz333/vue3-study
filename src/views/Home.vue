<template>
  <div class="home">
    <ComSetup />
    <ComReactive />
  </div>
</template>

<script>
// @ is an alias to /src
import ComSetup from "@/components/1.setup.vue";
import ComReactive from "@/components/2.reactive.vue";

export default {
  name: "Home",
  components: {
    ComSetup,
    ComReactive
  }
};
</script>
