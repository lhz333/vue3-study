<template>
  <div class="home">
    <ComSetup />
    <ComReactive />
    <ComRef />
  </div>
</template>

<script>
// @ is an alias to /src
import ComSetup from "@/components/1.setup.vue";
import ComReactive from "@/components/2.reactive.vue";
import ComRef from "@/components/3.ref.vue";

export default {
  name: "Home",
  components: {
    ComSetup,
    ComReactive,
    ComRef
  }
};
</script>
