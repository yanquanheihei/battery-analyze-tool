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
              :data="folderData"
              :props="defaultProps"
              @node-click="handleNodeClick">
          </el-tree>
        </div>
      </div>


    </div>
  </div>
</template>

<script>
import {ipcRenderer} from 'electron'
export default {
  name: 'FileList',
  data () {
    return {
      folderData: [],
      defaultProps: {
        children: 'children',
        label: 'label'
      },
      datePickValue: ''
    }
  },
  methods: {
    addFolder () {
      let ipc = ipcRenderer
      ipc.send('open-directory-dialog', 'openDirectory')

      let curFolderData = []
      ipc.once('selectedItem', (event, rootPath) => {
        this.$axios.get('http://localhost:5000/BatteryDatas/folderStruct', {
          params: {
            path: rootPath
          }
        }).then((response) => {
          let parents = response.data.parents

          parents.forEach(parentFolder => {
            let parent
            let childrens = []

            parentFolder.subFolders.forEach(subFolder => {
              childrens.push({label: subFolder.slice(subFolder.lastIndexOf('\\') + 1)})
            })
            parent = {
              label: parentFolder.parentName.slice(parentFolder.parentName.lastIndexOf('\\') + 1),
              children: childrens
            }

            curFolderData.push(parent)
          })
        }).catch((error) => {
          console.log(error)
        })
      })

      this.folderData = curFolderData
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
