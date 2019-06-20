<template>
    <div class="icons">
        <Swiper :autoPlay="false">
          <Slide v-for="(page,index) of pages" :key="index">
            <div class="icon" v-for="item of page" :key="item.id">
                <div class="icon-img">
                    <img class="icon-img-con" :src="item.imgUrl"/>
                </div>
                <p class="icon-desc">{{item.desc}}</p>
            </div>
          </Slide>
        </Swiper>
    </div>
</template>

<script>
import { Swiper, Slide } from 'vue-swiper-component'
export default {
  name: 'HomeIcons',
  components: {Swiper, Slide},
  props: {
    list: Array
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="scss" scoped>
    @import '~styles/varibles.scss';
    @import '~styles/mixins.scss';
    .icons{
        overflow: hidden;
        height: 0;
        padding-bottom: 50%;
        .icon{
            float: left;
            width: 25%;
            padding-bottom: 25%;
            position: relative;
            overflow: hidden;
            height: 0;
            .icon-img{
                position: absolute;
                top: 0;
                left: 0;
                right: 0;
                bottom: .44rem;
                box-sizing: border-box;
                padding: .1rem;
                .icon-img-con{
                    display: block;
                    height: 100%;
                    margin: 0 auto;
                }
            }
            .icon-desc{
                position: absolute;
                bottom: 0;
                left: 0;
                right: 0;
                height: .44rem;
                line-height: .44rem;
                text-align: center;
                color: $darkTextColor;
                @include ellips;
            }
        }
    }
</style>
