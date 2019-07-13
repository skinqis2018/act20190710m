<template>
  <div class="prize">
    <header>
      <img src="../imgs/arrow_03.jpg"/>
      <img src="../imgs/title_03.jpg"/>
      <img src="../imgs/arrow_03.jpg"/>
    </header>
    <div class="prize__list">
      <div class="prize__list__item">
        <img src="../imgs/qb_03.png"/>
        <span>需要50积分</span>
        <ActBtn 
        style="width: 8.4rem; margin: auto"
        text="领取"/>
      </div>
      <div class="prize__list__item">
        <img src="../imgs/qb_03.png"/>
        <span>需要50积分</span>
        <ActBtn 
        style="width: 8.4rem; margin: auto"
        text="领取"/>
      </div>
      <div class="prize__list__item">
        <img src="../imgs/qb_03.png"/>
        <span>需要50积分</span>
        <ActBtn 
        style="width: 8.4rem; margin: auto"
        text="领取"/>
      </div>
      <div class="prize__list__item">
        <img src="../imgs/qb_03.png"/>
        <span>需要50积分</span>
        <ActBtn 
        style="width: 8.4rem; margin: auto"
        text="领取"/>
      </div>
    </div>
    <div class="prize__score">我的积分：{{score}}</div>
    <div class="prize__task">
      <span class="prize__task__text">1.每日登录企鹅电竞且关注任意王者主播</span>
      <span class="prize__task__score">+50积分</span>
      <ActBtn
        style="display:inline-block; width: 6.8rem"
        text="领取"/>
    </div>
    <div class="prize__task">
      <span class="prize__task__text">2:观看WCG王者荣耀全球赛3分钟</span>
      <span class="prize__task__score">+50积分</span>
      <ActBtn
        disabled
        style="display:inline-block; width: 6.8rem"
        text="领取"/>
    </div>
    <div class="prize__task">
      <span class="prize__task__text">3.观看王者专区任意主播直播累计观看30分钟</span>
      <span class="prize__task__score">+50积分</span>
      <ActBtn
        disabled
        style="display:inline-block; width: 6.8rem"
        text="领取"/>
    </div>
    <div class="prize__task">
      <span class="prize__task__text">4.为任意王者专区的主播送出至少1个WCG你最强礼物</span>
      <span class="prize__task__score">+50积分</span>
      <ActBtn
        disabled
        style="display:inline-block; width: 6.8rem"
        text="领取"/>
    </div>
  </div>
</template>
<script>
import ActBtn from '../components/act-btn'

export default {
  components: {
    ActBtn
  },
  data () {
    return {
      score: 999999
    }
  }
}
</script>

