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
          label: '2021-06-11',
          children: [{label: '15:33:21'}, {label: '18:33:21'}, {label: '20:33:21'}, {label: '23:33:21'}]
        },
        {
          label: '2021-07-19',
          children: [{label: '15:33:21'}, {label: '18:33:21'}, {label: '20:33:21'}, {label: '23:33:21'}]
        },
        {
          label: '2021-08-01',
          children: [{label: '15:33:21'}, {label: '18:33:21'}, {label: '20:33:21'}, {label: '23:33:21'}]
        },
        {
          label: '2021-08-13',
          children: [{label: '15:33:21'}, {label: '18:33:21'}, {label: '20:33:21'}, {label: '23:33:21'}]
        },
        {
          label: '2021-08-21',
          children: [{label: '15:33:21'}, {label: '18:33:21'}, {label: '20:33:21'}, {label: '23:33:21'}]
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

.list-container {
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
