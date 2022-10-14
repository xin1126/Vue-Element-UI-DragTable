<template>
  <div class="home">
    <h1>Element UI + Sortablejs表格拖曳</h1>
    <el-table
      :data="tableData"
      border
      style="width: 100%"
      :row-class-name="tableRowClassName"
    >
      <el-table-column
        v-for="(value, key) of tableData[0]"
        :key="key"
        :prop="key"
        :label="labelText[key]"
        align="center"
      />
    </el-table>
  </div>
</template>

<script>
import Sortable from "sortablejs";
export default {
  props: ["tableData", "labelText", "tableRowClassName"],
  methods: {
    rowDrop() {
      const tbody = document.querySelector(".el-table__body-wrapper tbody");
      Sortable.create(tbody);
    }
  },
  mounted() {
    this.rowDrop();
  }
};
</script>
