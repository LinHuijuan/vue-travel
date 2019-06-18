<template>
    <div class="icons">
        <Swiper>
          <Slide v-for="(page,index) of pages" :key="index">
            <div class="icon" v-for="item of page" :key="item.id">
                <div class="icon-img">
                    <img class="icon-img-con" :src="item.imgurl"/>
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
  data () {
    return {
      iconsList: [
        {
          id: '0001',
          imgurl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '0002',
          imgurl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '0003',
          imgurl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '0004',
          imgurl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '0005',
          imgurl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '0006',
          imgurl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '0007',
          imgurl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '0008',
          imgurl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '0009',
          imgurl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '0010',
          imgurl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconsList.forEach((item, index) => {
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
