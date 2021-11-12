<template>
  <div class="panel">
      <h2>数据情况</h2>
        <el-table
          :data="tableData"
          height="3rem"
          style="width: 100%">
          <el-table-column
            prop="name"
            align="center"
            label="平台">
          </el-table-column>
          <el-table-column
            prop="newsnum"
            align="center"
            label="爬取新闻数量">
          </el-table-column>
          <el-table-column
            prop="usernum"
            align="center"
            label="爬取用户数量">
          </el-table-column>
        </el-table>
      <div class="panel-footer"></div>
  </div>
</template>

<script>
export default {
    name: '',
    data(){
        return{
          tableData: [{
            name: 'reddit',
            newsnum:'10',
            usernum: '20',
          },{
            name: 'reddit',
            newsnum:'10',
            usernum: '20',
          },{
            name: 'reddit',
            newsnum:'10',
            usernum: '20',
          }]
        }
    },
    mounted(){

    },
    methods:{
        
    }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">

</style>