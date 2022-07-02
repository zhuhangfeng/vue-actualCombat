<template>
  <div>
    <!-- 按钮 -->
    <el-button type="primary" size="medium" icon="el-icon-plus">添加</el-button>
    <el-table class="eltable" :data="tableData" border style="width: 100%">
      <el-table-column prop="date" label="序号" width="180"> </el-table-column>
      <el-table-column prop="name" label="品牌名称" width="180"> </el-table-column>
      <el-table-column prop="address" label="品牌LOGO"> </el-table-column>
      <el-table-column prop="address" label="操作"> </el-table-column>
    </el-table>
     <el-pagination
     style="textAlign:center"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
      :current-page="currentPage4"
      :page-sizes="[10, 29, 39, 40]"
      :page-size="10"
      layout="prev, pager, next, jumper,->, sizes,total"
      :total="400"
      :pager-count="9">
    </el-pagination>
    
  </div>
</template>

<script>
export default {
  name: "TradeMark",
   data() {
      return {
        tableData: [{
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄'
        }],
        currentPage4: 6
      }
    },
     methods: {
      handleSizeChange(val) {
        console.log(`每页 ${val} 条`);
      },
      handleCurrentChange(val) {
        console.log(`当前页: ${val}`);
      }
    },
};
</script>

<style lang="scss" scoped>
  .eltable{
    margin-top:20px
  }
  // .elpagination{
  //   text-align: center;
  // }
  
</style>