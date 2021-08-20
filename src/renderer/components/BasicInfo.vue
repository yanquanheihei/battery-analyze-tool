<template>
  <div class="block">
    <span class="demonstration"></span>
    <el-carousel height="200px">
      <!--      <el-carousel-item v-for="item in 4" :key="item">-->
      <!--        <h3 class="small">{{ item }}</h3>-->
      <!--      </el-carousel-item>-->
      <el-carousel-item>
        <card-view card-name="基础信息"></card-view>
      </el-carousel-item>
<!--      <el-carousel-item>-->
<!--        <card-view card-name="电池总电流"></card-view>-->
<!--      </el-carousel-item>-->
<!--      <el-carousel-item>-->
<!--        <card-view card-name="空气检测器型号"></card-view>-->
<!--      </el-carousel-item>-->
<!--      <el-carousel-item>-->
<!--        <card-view card-name="电子鼻运行时间"></card-view>-->
<!--      </el-carousel-item>-->
    </el-carousel>
  </div>
</template>

<script>
import CardView from './CardView'

export default {
  name: 'BasicInfo',
  components: {CardView},
  comments: {
    'card-view': CardView
  }
}
</script>

<style scoped>
.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 150px;
  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n+1) {
  background-color: #d3dce6;
}

.demonstration {
  font-size: 13px;
}
</style>
