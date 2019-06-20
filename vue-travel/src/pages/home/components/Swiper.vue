<template>
    <div class="wrapper">
        <Swiper  v-if="showSwiper">
          <Slide v-for="(item,index) in list" :key="index">
            <img class="swiper-img" :src="item.imgUrl" />
          </Slide>
        </Swiper>
    </div>
</template>

<script>
import { Swiper, Slide } from 'vue-swiper-component'
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  components: {Swiper, Slide},
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
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
    padding-bottom: 31.25%;
    background: $bgColor;
    .swiper-img{
      width: 100%;
    }
  }
</style>
