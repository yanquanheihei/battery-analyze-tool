<template>
  <div>
    <div class="container">
      <div class="button-container">
        <el-button type="primary" icon="el-icon-folder-add" @click="addFolder">导入</el-button>
      </div>
      <div class="list-container">
        <div class="date-picker-container">
          <el-date-picker
              style="width: 240px"
              class="date-picker"
              v-model="datePickValue"
              type="daterange"
              size="mini"
              start-placeholder="开始日期"
              end-placeholder="结束日期"
              :default-time="['00:00:00', '23:59:59']">
          </el-date-picker>
        </div>
        <div class="tree-container">
          <el-tree
              :data="data"
              :props="defaultProps"
              accordion
              @node-click="handleNodeClick">
          </el-tree>
        </div>
      </div>


    </div>
  </div>
</template>

<script>
export default {
  name: 'FileList',
  data () {
    return {
      data: [
        {
          label: '一级 1',
          children: [{
            label: '二级 1-1',
            children: [{
              label: '三级 1-1-1'
            }]
          }]
        },
        {
          label: '一级 2',
          children: [{
            label: '二级 2-1',
            children: [{
              label: '三级 2-1-1'
            }]
          }, {
            label: '二级 2-2',
            children: [{
              label: '三级 2-2-1'
            }]
          }]
        },
        {
          label: '一级 3',
          children: [{
            label: '二级 3-1',
            children: [{
              label: '三级 3-1-1'
            }]
          }, {
            label: '二级 3-2',
            children: [{
              label: '三级 3-2-1'
            }]
          }]
        }
      ],
      defaultProps: {
        children: 'children',
        label: 'label'
      },
      datePickValue: ''
    }
  },
  methods: {
    addFolder () {
      alert('hello')
    },
    handleNodeClick () {
    }
  }
}
</script>

<style>

.container {
  padding-top: 10px;
  display: grid;
  grid-template-areas:
      "button button"
      "list list";
      /*"eventTime-picker eventTime-picker"*/
      /*"tree tree";*/
  grid-template-rows: 1fr 7fr;
  grid-gap: 10px;
}

.button-container {
  margin: 0 auto;
  /*padding-bottom: 5px;*/
  grid-area: button;
  /*border-bottom: 1px solid skyblue;*/
}

.list-container{
  margin: 0 auto;
  grid-area: list;
  border-top: 1px solid skyblue;
}

.date-picker-container {
  padding-top: 5px;
  padding-bottom: 5px;
  /*margin: 0 auto;*/
  /*grid-area: eventTime-picker;*/
  /*padding-bottom: 5px;*/
  /*border-bottom: 1px solid skyblue;*/
}

.tree-container {
  padding-top: 5px;
  border-top: 1px solid skyblue;
  /*grid-area: tree;*/
}
</style>
