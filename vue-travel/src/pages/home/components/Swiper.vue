<template>
    <div class="wrapper">
        <Swiper>
          <Slide v-for="(item,index) in swiperList" :key="index">
            <img class="swiper-img" :src="item.imgUrl" />
          </Slide>
        </Swiper>
    </div>
</template>

<script>
import { Swiper, Slide } from 'vue-swiper-component'
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperList: [
        {
          imgUrl: 'https://img1.qunarzz.com/vc/98/a0/cd/bc0b283fc4e3b9d25136688bc5.jpg'
        },
        {
          imgUrl: 'https://img1.qunarzz.com/vc/07/aa/fc/147086c7e45caf75337336dc9b.jpg'
        }
      ]
    }
  },
  components: {Swiper, Slide}
}
</script>

<style lang='stylus' scoped>
  .wrapper /deep/ .wh_show_bgcolor{
    background: #fff;
  }
  .wrapper{
    overflow: hidden;
    width: 100%;
    height: 0;
    padding-bottom: 30%;
    background: $bgColor;
    .swiper-img{
      width: 100%;
    }
  }
</style>
