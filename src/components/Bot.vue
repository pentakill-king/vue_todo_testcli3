<template>

  <div class="bot">

    <el-row>

      <el-button
        @click="All"
        plain
      >all</el-button>

      <el-button
        plain
        @click="del"
      >clear</el-button>

    </el-row>

  </div>

</template>

<script>
export default {
  //全选删除 from list
  props: { mycity: Object, CheckAll: Function, clear: Function },

  methods: {
    All() {
      this.CheckAll();
    },
    del() {
      this.clear();
    }
  }
};
</script>

 <style lang="less" scoped>
.bot {
  margin-top: 1em;
}
</style>