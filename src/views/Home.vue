<template>
  <div class="home">
    <ComSetup />
    <ComReactive />
    <ComRef />
    <ComToRefs />
    <ComComputed />
  </div>
</template>

<script>
// @ is an alias to /src
import ComSetup from "@/components/1.setup.vue";
import ComReactive from "@/components/2.reactive.vue";
import ComRef from "@/components/3.ref.vue";
import ComToRefs from "@/components/4.toRefs.vue";
import ComComputed from "@/components/5.computed.vue";

export default {
  name: "Home",
  components: {
    ComSetup,
    ComReactive,
    ComRef,
    ComToRefs,
    ComComputed
  }
};
</script>
