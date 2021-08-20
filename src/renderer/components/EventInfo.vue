<template>
  <div class="container">
    <el-table
        :data="tableData"
        border
        fit:false
        style="width: 100%"
        :cell-style="tableCellStyle"
        :header-cell-style="tableHeaderStyle">
      <el-table-column
          prop="eventTime"
          label="时间"
      width="135px">
      </el-table-column>
      <el-table-column
          prop="eventName"
          label="事件名称"
          width="120px">
      </el-table-column>
      <el-table-column
          prop="eventType"
          label="事件动作"
          width="80px">
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  name: 'EventInfo',
  data () {
    return {
      tableData: [{
        eventTime: '2016-05-02 16:28:41',
        eventName: '硬盘录像机',
        eventType: '打开'
      }, {
        eventTime: '2016-05-04 16:28:41',
        eventName: '空气质量检测仪',
        eventType: '关闭'
      }, {
        eventTime: '2016-05-01 16:28:41',
        eventName: '辐射探测器',
        eventType: '打开'
      }, {
        eventTime: '2016-05-03 16:28:41',
        eventName: '拉曼检测器',
        eventType: '关闭'
      }, {
        eventTime: '2016-05-03 16:28:41',
        eventName: '痕量监测仪',
        eventType: '关闭'
      }, {
        eventTime: '2016-05-03 16:28:41',
        eventName: '蓝牙测温仪',
        eventType: '关闭'
      }, {
        eventTime: '2016-05-03 16:28:41',
        eventName: '拉曼检测器',
        eventType: '关闭'
      }]
    }
  },
  methods: {
    tableHeaderStyle ({row, column, rowIndex, columnIndex}) {
      return 'text-align:center;background-color:#D3DCE6;fontFamily:Helvetica;fontSize:14px'
    },
    tableCellStyle ({row, column, rowIndex, columnIndex}) {
      return 'text-align:center;color:#666;fontFamily:Arial;fontSize:12px'
    }
  }
}
</script>
<style scoped>
.container {
  display: block;
  margin: 0 auto;
  padding: 0 3px 3px;
}
</style>
