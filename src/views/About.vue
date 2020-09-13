<template>
  <div class="about">
    <ComWatch />
    <ComWatchStop />
  </div>
</template>

<script>
import ComWatch from "@/components/6.watch.vue";
import ComWatchStop from "@/components/7.watch-stop.vue";
export default {
  components: { ComWatch, ComWatchStop }
};
</script>
