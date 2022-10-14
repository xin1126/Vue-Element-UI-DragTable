<template>
  <div class="container">
    <Sortable
      class="item"
      :tableData="tableData"
      :labelText="labelText"
      :tableRowClassName="tableRowClassName"
    />
    <Draggable
      class="item"
      :tableData="tableData"
      :labelText="labelText"
      :tableRowClassName="tableRowClassName"
    />
  </div>
</template>

<script>
import Sortable from "@/components/Sortable.vue";
import Draggable from "@/components/Draggable.vue";
export default {
  components: {
    Sortable,
    Draggable
  },
  data() {
    return {
      tableData: [
        {
          name: "小美",
          age: "15",
          gender: "女性",
          address: "台北市"
        },
        {
          name: "小王",
          age: "30",
          gender: "男性",
          address: "新竹市"
        },
        {
          name: "小花",
          age: "26",
          gender: "女性",
          address: "高雄市"
        },
        {
          name: "小明",
          age: "17",
          gender: "男性",
          address: "新北市"
        }
      ],
      labelText: {
        name: "名稱",
        age: "年齡",
        gender: "性別",
        address: "地址"
      }
    };
  },
  methods: {
    tableRowClassName({ row, rowIndex }) {
      console.log(row);
      if (rowIndex === 1) return "warning-row";
      if (rowIndex === 3) return "success-row";
      return "";
    }
  }
};
</script>

<style lang="scss">
.home {
  width: 800px;
  margin: 0 auto;
}

.el-table .warning-row {
  background: oldlace;
}

.el-table .success-row {
  background: #f0f9eb;
}

.el-table__row {
  cursor: pointer;
}

.container {
  display: flex;
  .item {
    width: 40%;
  }
}
</style>
