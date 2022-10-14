<template>
  <div class="home">
    <h1>Element UI + Draggable表格拖曳</h1>
    <el-table-draggable>
      <el-table
        :data="[...tableData]"
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
    </el-table-draggable>
  </div>
</template>

<script>
import ElTableDraggable from "element-ui-el-table-draggable";
export default {
  props: ["tableData", "labelText", "tableRowClassName"],
  components: {
    ElTableDraggable
  }
};
</script>
