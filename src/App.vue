<template>
  <div id="app">
    <header>
      <img src="./imgs/header_banner.jpg"/>
      <ActBtn 
      v-if="!isDownload || !isApp || !isLogin"
      class="header__btn"
      :text="isApp ? '登录领奖' : isDownload ? '启动企鹅电竞' : '下载企鹅电竞'"
      style="width: 10rem"/>
    </header>
    <ActVideos />
    <ActPrize />
    <div class="notice">
      <header>
        <img src="./imgs/arrow_03.jpg"/>
        <img src="./imgs/title_07.jpg"/>
        <img src="./imgs/arrow_03.jpg"/>
      </header>
      <img src="./imgs/notice_03.png"/>
      <ActBtn 
      class="notice__btn"
      text="点击观赛"
      style="width: 10rem"/>
    </div>
    <ActStars />
    <footer>
      <img src="./imgs/footer_link.jpg"/>
      <div>腾讯公司保留在法律规定范围内对上述规则进行解释的权利</div>
    </footer>
    <ActMask 
      v-show="openMask"/>
  </div>
</template>

<script>
  import './assets/less/common.less'
  import ActBtn from './components/act-btn'
  import ActVideos from './components/act-videos'
  import ActPrize from './components/act-prize'
  import ActStars from './components/act-stars'
  import ActMask from './components/act-mask'

  export default {
    name: 'App',
    components: {
      ActBtn,
      ActVideos,
      ActPrize,
      ActStars,
      ActMask
    },
    data () {
      return {
        isApp: false,
        isLogin: false,
        isDownload: false,
        openMask: false
      }
    },
    created () {
      window.eventBus.$on('openMask', () => {
        if (!this.isApp) {
          this.openMask = true
        }
      })
    }
  }
</script>
