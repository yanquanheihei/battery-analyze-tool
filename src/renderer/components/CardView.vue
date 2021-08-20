<template>
  <div>
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <span class="title">{{ cardName }}</span>
        <el-button style="float: right; padding: 3px 0" type="text">信息导出</el-button>
      </div>
      <!--      <div v-for="o in 4" :key="o" class="text item">-->
      <!--        {{ '列表内容 ' + o }}-->
      <!--      </div>-->
      <div class="cardContainer">
        <div class="first">
          <label>电池电量（AH）：50</label>
        </div>
        <div class="second">
          <label>硬盘录像机额定功耗（W）：15</label>
        </div>
        <div class="third">
          <label>空气检测仪额定功耗（W）：30</label>
        </div>
        <div class="fore">
          <label>拉曼检测仪额定功耗（W）：20</label>
        </div>
        <div class="five">
          <label>辐射探测仪功耗（W）：15</label>
        </div>
        <div class="six">
          <label>蓝牙测温仪额定功耗（W）：5</label>
        </div>
      </div>
    </el-card>
  </div>
</template>

<script>
export default {
  name: 'CardView',
  props: {
    cardName: ''
  }
}
</script>

<style scoped>
.text {
  font-size: 13px;
}

.item {
  margin-bottom: 15px;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}

.clearfix:after {
  clear: both
}

.box-card {
  width: 100%;
}

.title {
  font-family: "Microsoft YaHei UI", sans-serif;
  font-size: 14px;
  font-weight: bold;
}

.cardContainer {
  font-size: 13px;
  font-family: "Microsoft YaHei UI",sans-serif;
  display: grid;
  grid-template-rows: 1fr 1fr 1fr;
  grid-template-columns: 1fr 1fr;
  grid-gap: 26px;
}
</style>
