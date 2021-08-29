<template>
  <div class="swiper-container basicinfoswiper">
    <div class="swiper-wrapper">
      <slot></slot>
    </div>
    <div class="swiper-pagination" slot="pagination"></div>
  </div>
</template>
<script>
import Swiper from 'swiper'
import 'swiper/dist/css/swiper.css'
import 'swiper/dist/css/swiper.min.css'

export default {
  mounted () {
    /* eslint-disable no-new */
    new Swiper('.basicinfoswiper', {
      loop: true,
      speed: 3000,
      // autoplay: {
      //   delay: 2000,
      //   disableOnInteraction: false,
      //   reverseDirection: false
      // },
      pagination: {
        el: '.swiper-pagination',
        type: 'bullets',
        bulletElement: 'li',
        hideOnClick: true,
        clickable: true,
        paginationClickable: true
      },
      spaceBetween: 20,
      freeMode: true,
      slidesPerView: 2,
      centeredSlides: true
    })
  },
  data () {
    return {
    }
  }
}
</script>
<style scoped>
.swiper-pagination-bullet-active {
    background-color: #52B54B
}
</style>