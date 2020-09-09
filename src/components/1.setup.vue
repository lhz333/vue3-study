<template>
  <div>测试setup</div>
</template>
<script>
export default {
  name: "",
  data() {
    return {};
  },
  components: {},
  props: {},
  computed: {},
  methods: {},
  beforeCreate() {
    console.log("this is beforeCreate");
  },
  setup() {
    // setup函数在生命周期函数beforeCreate和created之间执行
    console.log("this is setup");
  },
  created() {
    console.log("this is created");
  },
  mounted() {},
  watch: {}
};
</script>

<style lang="less" scoped></style>
