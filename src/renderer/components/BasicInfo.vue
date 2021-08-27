<template>
  <div class="block">
    <custom-swiper class="swiper">
        <div class="swiper-slide">
            <label>电池电量（AH）</label>
            <label>50</label>
            <label>SN4123414</label>
        </div>
        <div class="swiper-slide">
            <label>硬盘录像机额定功耗（W）</label>
            <label>15</label>
            <label>SN767868</label>
        </div>
        <div class="swiper-slide">
            <label>空气检测仪额定功耗（W）</label>
            <label>30</label>
            <label>SN97799977</label>
        </div>
        <div class="swiper-slide">
            <label>拉曼检测仪额定功耗（W）</label>
            <label>20</label>
            <label>SN53534534</label>
        </div>
        <div class="swiper-slide">
            <label>辐射探测仪功耗（W）</label>
            <label>15</label>
            <label>SN57577755</label>
        </div>
        <div class="swiper-slide">
            <label>蓝牙测温仪额定功耗（W）</label>
            <label>5</label>
            <label>SN987978987</label>
        </div>   
        </custom-swiper>   
  </div>
</template>

<script>
import CustomSwiper from '../components/CustomSwiper'

export default {
  name: 'BasicInfo',
  components: {
    'custom-swiper': CustomSwiper
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

.swiper{
  width: 100%;
  margin: 0 auto;
  overflow: hidden;
  background-color: #E9EEF3;
}

.swiper-slide{
  display: flex;
  flex-flow: column;
  /* width: 100%; */
  margin: 3px;
  background-color: #B3C0D1;
  border: 2px solid lightcyan;
  border-radius: 5px;
}
label{
  padding: 15px;
    font-family: "Microsoft YaHei UI",serif;
  font-size: 14px;
}
</style>
