<template>
  <div class="mask">
    <div class="mask__bg"></div>
    <div class="mask__content">
      <header>
        <div class="mask__content__title">你还没有登录企鹅电竞，不能够参与抽奖哦!</div>
        <div>马上登录看WCG赛事、还有大神主播带你上分，领海量游戏礼包!</div>
      </header>
      <div class="mask__content__prize">
        <div class="mask__content__prize__item">
          <div>WCG赛事(独家)</div>
          <img src="../imgs/prize_03.jpg">
        </div>
        <div class="mask__content__prize__item">
          <div>主播开黑</div>
          <img src="../imgs/prize_03.jpg">
        </div>
        <div class="mask__content__prize__item">
          <div>游戏礼包</div>
          <img src="../imgs/prize_03.jpg">
        </div>
        <div class="mask__content__prize__item">
          <div>
            <span>现金红包</span>
            <span>(新人专属)</span>
          </div>
          <img src="../imgs/prize_03.jpg">
        </div>
      </div>
      <ActBtn
        class="mask__content__btn"
        text="前往企鹅电竞"
        style="width: 10rem"/>
    </div>
  </div>
</template>
<script>
import ActBtn from '../components/act-btn'

export default {
  components: {
    ActBtn
  }
}
</script>

