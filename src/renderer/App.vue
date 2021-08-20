<template>
  <div id="app">
    <el-container>
      <el-header class="header-title" height="30px">
<!--        电池健康状态分析软件-->
        <title-button type="min"/>
        <title-button type="max"/>
        <title-button type="close"/>
      </el-header>
      <el-container>
        <el-aside width="250px">
          <file-list></file-list>
        </el-aside>
        <el-container class="mainContainer" direction="vertical">
          <div class="batteryCurve">
            <battery-curve></battery-curve>
          </div>
          <div class="basicInfo">
            <basic-info></basic-info>
          </div>
        </el-container>
        <el-aside width="342px">
          <event-info></event-info>
        </el-aside>
      </el-container>
      <el-footer height="30px">
        <div class="footer-info">版权所有© 2011 All Right Reserved 同方威视技术股份有限公司</div>
      </el-footer>
    </el-container>
  </div>
</template>

<script>
import TitleButton from './components/TitleButton'
import FileList from './components/FileList'
import BatteryCurve from './components/BatteryCurve'
import BasicInfo from './components/BasicInfo'
import EventInfo from './components/EventInfo'

export default {
  name: 'battery-analyze-tool',
  components: {
    'title-button': TitleButton,
    'file-list': FileList,
    'battery-curve': BatteryCurve,
    'basic-info': BasicInfo,
    'event-info': EventInfo
  }
}
</script>

<style>

html, body, #app, .el-container {
  padding: 0;
  margin: 0;
  height: 100%;
  width: 100%;
}

.el-header, .el-footer {
  background-color: #B3C0D1;
  color: #333;
  text-align: center;
  line-height: 30px;
}

.el-header {
  font-family: "Microsoft YaHei UI", serif;
  font-weight: bold;
  font-size: 12px;
}

.el-aside {
  background-color: #D3DCE6;
  color: #333;
  text-align: center;
}

.el-main {
  background-color: #E9EEF3;
  color: #333;
  /*text-align: center;*/
  /*line-height: 160px;*/
}

body > .el-container {
  margin-bottom: 40px;
}

.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
}

.el-container:nth-child(7) .el-aside {
  line-height: 100%;
}

/*标题栏*/
.header-title {
  /*position: absolute;*/
  width: 100%;
  height: 100%;
  -webkit-app-region: drag;
}

.batteryCurve {
  /*height: 100%;*/
}
.footer-info{
  font-family: "Microsoft YaHei UI",serif;
  font-size: 14px;
}

</style>
