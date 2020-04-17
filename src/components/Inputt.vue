<template>
  <div>
    <!-- ui入坑 -->
    <el-input
      clearable
      placeholder="what are you 弄啥呢"
      @keyup.enter.native="change"
      v-model="mycity.input"
    >
    </el-input>
  </div>
</template>

<script>
export default {
  methods: {
    change() {

      var mycity;
      mycity = this.mycity;
      // 增
      if (mycity.input != "") {
        mycity.cities.unshift(mycity.input);
      }

      mycity.input = "";
    }
  },

  data() {
    return {};
  },

  props: { mycity: Object }
};

</script>

 <style lang="less" scoped>
</style>