<template>
  <div>

    <Inputt :mycity="mycity" />

    <Item :mycity="mycity" />
    <Bot
      :mycity="mycity"
      :CheckAll="CheckAll"
      :clear="delall"
    />

  </div>
</template>


<script>
// 引入组件输入框，底部组件
import Inputt from "@/components/Inputt.vue";
import Bot from "@/components/Bot.vue";
import Item from "@/components/Item.vue";

// 为了不尴尬的初始值;
var cityOptions = [
  "一血.............................................",
  "双杀",
  "三杀",
  "4杀",
  "pentakill"
];
export default {
  // 输入框，底部，列表
  components: {
    Inputt,
    Bot,
    Item
  },
  // 数据在此
  data() {
    return {
      //懒得改了直接用默认名吧 一入ui坑似海 切记
      mycity: {
        checkAll: false,
        checkedCities: [],
        cities: cityOptions,
        input: "",
        isdel: [false, false],
        iscmp: []
      }
    };
  },

  methods: {
    // 全删
    delall() {
      this.mycity.cities.splice(0, this.mycity.cities.length);
      this.mycity.checkedCities.length = 0;
    },
    // 全选
    CheckAll() {
      var checkAll = this.mycity.checkAll;
      this.mycity.checkedCities = checkAll ? this.mycity.cities : [];

      //  if(this.mycity.checkAll){this.mycity.checkedCities = this.mycity.cities}else{this.mycity.checkedCities = []}

      this.mycity.checkAll = !checkAll;
    }
  }
};
</script>

 <style lang="less" scoped>
</style>