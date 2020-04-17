<template>

  <div class="itm">

    <span class="benk">......<span class="tt">
        {{this.mycity.cities.length}}
      </span>
      ......items
      ......
      <span class="tt
    ">{{this.mycity.checkedCities.length}}</span>
      ......compeleted
    </span>
    <el-checkbox-group v-model="mycity.checkedCities">
      <el-checkbox
        v-model="mycity.checkedCities"
        @mouseenter.native="change(index,true)"
        @mouseleave.native="change(index,false)"
        class="line"
        v-for="(city,index) in mycity.cities"
        :label="city"
        :key="index"
        border
      >

        <div>{{city}}
          <span class="del">
            <div v-show="mycity.isdel[index]">
              <label
                @click="del(index)"
                slot="prefix"
                type="info"
                circle
                class="el-icon-error"
              ></label>
            </div>
          </span>
        </div>

      </el-checkbox>
    </el-checkbox-group>

  </div>
</template>

<script>
export default {
  props: { mycity: Object, CheckAll: Function },
  data() {
    return {};
  },

  methods: {
    // 单删
    del(index) {
      this.mycity.cities.splice(index, 1);
    },
    // pc专用
    change(index, isdel) {
      this.mycity.isdel[index] = isdel;
    }
  }
};
</script>

 <style lang="less" scoped>
.benk {
  border-bottom: 1px solid wheat;
  color: rgb(255, 8, 202);
}

.tt {
  color: turquoise;
  font-size: 2em;
}

.line {
  margin: 10em;
  padding: 0;
  background: #000;
  display: flex;
  text-align: center;
  font-size: 2em;
}
.del {
  display: flex;
  float: right;
}
.total {
  display: flex;
  padding-left: 50%;
}
</style>