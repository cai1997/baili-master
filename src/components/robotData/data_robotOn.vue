<template>
  <div class="panel">
    <h2>机器人运行详情</h2>
    <el-table :data="tableData" height="3rem" style="width: 100%">
      <el-table-column prop="name" align="center" label="平台">
      </el-table-column>
      <el-table-column prop="status" align="center" label="运行状态">
        <template slot-scope="scope">
          <span :style="{ color: status[scope.row.status].color }">{{
            status[scope.row.status].txt
          }}</span>
        </template>
      </el-table-column>
      <el-table-column prop="address" align="center" label="位置">
      </el-table-column>
      <el-table-column prop="date" align="center" label="发送时间">
      </el-table-column>
    </el-table>
    <div class="panel-footer"></div>
  </div>
</template>

<script>
export default {
  name: "dataRobotOn",
  props: {
    robotRunCondition: {
      type: Array,
    },
  },
  data() {
    return {
      status: {
        0: { txt: "故障", color: "#ff4546" },
        1: { txt: "运行中", color: "#67c23a" },
        2: { txt: "休息暂停", color: "#ffeb7b" },
      },
      tableData: [
        {
          name: "reddit",
          status: 0,
          ID: "1",
          type: "机器人",
          address: "afuhan",
          date: "2021/9/08",
        },
        {
          name: "reddit",
          status: 1,
          ID: "1",
          type: "机器人",
          address: "afuhan",
          date: "2021/9/08",
        },
        {
          name: "reddit",
          status: 2,
          ID: "1",
          type: "机器人",
          address: "afuhan",
          date: "2021/9/08",
        },
        {
          name: "reddit",
          status: 1,
          ID: "1",
          type: "机器人",
          address: "afuhan",
          date: "2021/9/08",
        },
        {
          name: "reddit",
          status: 0,
          ID: "1",
          type: "机器人",
          address: "afuhan",
          date: "2021/9/08",
        },
      ],
    };
  },
  mounted() {},
  methods: {},
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
</style>