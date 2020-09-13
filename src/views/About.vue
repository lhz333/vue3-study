<template>
  <div class="about">
    <ComWatch />
    <ComWatchStop />
    <ComWatchClean />
  </div>
</template>

<script>
import ComWatch from "@/components/6.watch.vue";
import ComWatchStop from "@/components/7.watch-stop.vue";
import ComWatchClean from "@/components/8.watch-clean.vue";
export default {
  components: { ComWatch, ComWatchStop, ComWatchClean }
};
</script>
