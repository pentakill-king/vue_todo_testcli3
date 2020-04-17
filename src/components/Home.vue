<template>
  <div class=home>
    <el-container>
      <el-header>
        <div class="todos">todos</div>
      </el-header>
      <el-main>
        <!-- 主要组件 -->
        <List />
      </el-main>
      <el-footer>
        <span class="tks">thanks for my daddy and cctv </span>
      </el-footer>

    </el-container>

  </div>

</template>

<script>
import List from "@/components/List.vue";

export default {
  name: "home",

  components: {
    List
  },

  methods: {}
};
</script>

<style lang="less" scoped>
.tks {
  text-align: center;

  bottom: 10em;
}
/deep/ .el-input__inner {
  &::placeholder {
    color: rgb(241, 241, 241);
  }
  background: rgb(37, 37, 37);
  color: rgb(161, 161, 161);
}

/deep/ .el-checkbox {
  margin: 0;
  padding: 0;
}

.home {
  background-color: black;
  padding: 1em;
}
.todos {
  color: coral;
  font-size: 5em;
  position: relative;
  transform: translate(0, -20%);
}

/deep/ .el-checkbox__label {
  text-align: left;
  padding-right: 1em;
  overflow: hidden;
  color: rgb(102, 204, 7);
  width: 100%;
}
/deep/ .el-checkbox.is-bordered {
  display: flex;
  height: 100%;
  width: 100%;
  background: rgb(39, 39, 39);
}
/deep/ .el-checkbox.is-bordered + .el-checkbox.is-bordered {
  margin: 0;
}

/deep/ .el-button {
  background-color: rgb(32, 32, 32);
}

/deep/ .el-checkbox__inner {
  background-color: rgb(180, 180, 180);
}
</style>
