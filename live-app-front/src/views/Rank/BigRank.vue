<template>
  <div class="Ra-swiper">
    <swiper :options="swiperOptionB"
            ref="mySwiperB">
      <!-- slides -->
      <swiper-slide class="sB"
                    :key="index"
                    v-for="(n,index) in data">
        <rank :data="n" />
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination swiper-paginationB"
           slot="pagination"></div>
    </swiper>
  </div>

</template>

<script>
import SmallRank from '../../components/Rank/SmallRank'
export default {
  name: 'Star',
  components: {
    "rank": SmallRank,
  },
	props: ['data'],
  data () {
    return {
			info: null,
      swiperOptionB: {
        // touchReleaseOnEdges: true, // 滑动到边缘是释放滑动
        pagination: {
          el: '.swiper-paginationB',
          clickable: true,  // 分页器点击
          renderBullet: function (index, className) {
            let text;
							switch (index) {
								case 0: text = '明星榜'; break;
								case 1: text = '财富榜'; break;
								case 2: text = '幸运榜'; break;
							}
							return '<span class="' + className + '">' + text + '</span>';
          },
          bulletClass: 'my-bulletB',//需设置.my-bullet样式
          bulletActiveClass: 'my-bullet-activeB', //分页器内当前活动块的指示小点的类名。
        }
      }
    }
  },
}
</script>
<style lang="scss">
.Ra-swiper {
  overflow-x: hidden;
  width: 100vw;

  .swiper-paginationB {
    display: flex;
    padding: 0.18rem 0.5rem 0.16rem;
    box-sizing: border-box;
    height: 0.62rem;
    justify-content: space-between;
    position: absolute;
    top: 0rem;
    .my-bulletB {
      color: #e1f5fc;
      font-size: 0.17rem;
      outline: none;
    }
  }
  .my-bullet-activeB {
    color: #fff !important;
    position: relative;
    &::after {
      content: "";
      width: 0.2rem;
      height: 0.02rem;
      position: absolute;
      bottom: 0rem;
      left: 0.15rem;
      background-color: #fff;
    }
  }
  .sB {
    margin-top: 0.55rem;
  }
}
</style>