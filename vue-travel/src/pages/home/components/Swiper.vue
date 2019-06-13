<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img class="swiper-img" :src="item.imgUrl" />
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: '0001',
          imgUrl: 'https://img1.qunarzz.com/vc/98/a0/cd/bc0b283fc4e3b9d25136688bc5.jpg'
        },
        {
          id: '0002',
          imgUrl: 'https://img1.qunarzz.com/vc/07/aa/fc/147086c7e45caf75337336dc9b.jpg'
        }
      ]
    }
  }
}
</script>

<style lang='stylus' scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 31.25%
    background: $bgColor
    .swiper-img
      width: 100%
</style>
