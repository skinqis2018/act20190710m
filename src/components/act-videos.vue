<template>
  <div class="videos">
    <header>
      <img src="../imgs/title_arrow.png" />
      <img src="../imgs/videos_title.png" />
      <img src="../imgs/title_arrow.png" />
    </header>
    <div class="videos__tabs">
      <div 
        class="videos__tabs__tab"
        :class="{active : active}"
        @click="toLive">
        热门直播
      </div>
      <div 
        class="videos__tabs__tab"
        :class="{ active : !active }"
        @click="toList">
        往期精彩
      </div>
    </div>
    <div v-show="active" class="videos__box">
      <div class="videos__box__content">
        <img :src="video.poster || require('../imgs/default.jpg')" />
        <div v-show="block" class="videos__box__content__mask"></div>
        <div v-show="block" class="videos__box__content__note">
          <header>登录企鹅电竞，观看高清直播，</header>
          <div>还有海量礼物等你来领</div>
          <footer>
            <ActBtn 
              text="以后再说"
              style="width: 10rem" />
            <ActBtn 
              text="前往观看"
              style="width: 10rem" />
          </footer>
        </div>
      </div>
      <div class="videos__box__info">
        <div class="videos__box__info__opening">
          <img 
            v-show="lives.length > 0"
            src="../imgs/date.png" />
          <span
            v-show="lives.length > 0">
            {{ video.date }}
          </span>
          <span
            v-show="lives.length > 0">
            {{ video.time }}
          </span>
        </div>
        <div class="videos__box__info__change">
          <img 
            src="../imgs/videos_arrow.png" 
            @click="pre" />
          <div 
            v-show="lives.length > 0"
            class="videos__box__info__change__teams">
            <div class="videos__box__info__change__teams__item">
              <div>{{ video.leftEN }}</div>
              <div>From: {{ video.leftZH }}</div>
              <em></em>
            </div>
            <img src="../imgs/vs.png" />
            <div class="videos__box__info__change__teams__item">
              <div>{{ video.rightEN }}</div>
              <div>From: {{ video.rightZH }}</div>
              <em></em>
            </div>
          </div>
          <div 
            v-show="lives.length == 0"
            class="videos__box__info__change__null">
            <div>当前还没有赛事，先来看大神直播</div>
            <div>带你上分吧</div>
          </div>
          <img 
            class="videos__box__info__change__next" 
            src="../imgs/videos_arrow.png" 
            @click="next" />
        </div>
      </div>
    </div>
    <div v-show="!active" class="videos__box">
      <div class="videos__box__content">
        <img :src="video.poster || require('../imgs/default.jpg')" />
        <div v-show="block" class="videos__box__content__mask"></div>
        <div 
          v-show="block" 
          class="videos__box__content__note">
          <header>登录企鹅电竞，观看高清直播，</header>
          <div>还有海量礼物等你来领</div>
          <footer>
            <ActBtn 
              text="以后再说"
              style="width: 10rem" />
            <ActBtn 
              text="前往观看"
              style="width: 10rem" />
          </footer>
        </div>
      </div>
      <div class="videos__box__info">
        <div class="videos__box__info__opening">
          <img 
            v-show="list.length > 0"
            src="../imgs/date.png" />
          <span
            v-show="list.length > 0">
            {{ video.date }}
          </span>
          <span
            v-show="list.length > 0">
            {{ video.time }}
          </span>
        </div>
        <div class="videos__box__info__change">
          <img 
            src="../imgs/videos_arrow.png"
            @click="listPre" />
          <div 
            v-show="list.length > 0"
            class="videos__box__info__change__teams">
            <div class="videos__box__info__change__teams__item">
              <div>{{ video.leftEN }}</div>
              <div>From: {{ video.leftZH }}</div>
              <em></em>
            </div>
            <img src="../imgs/vs.png" />
            <div class="videos__box__info__change__teams__item">
              <div>{{video.rightEN}}</div>
              <div>From: {{ video.rightZH }}</div>
              <em></em>
            </div>
          </div>
          <div 
            v-show="list.length == 0"
            class="videos__box__info__change__null">
            <div>当前还没有赛事，先来看大神直播</div>
            <div>带你上分吧</div>
          </div>
          <img 
            src="../imgs/videos_arrow.png"
            class="videos__box__info__change__next" 
            @click="listNext" />
        </div>
      </div>
    </div>
    <footer>
      <ActBtn 
        class="videos__btn"
        text="前往围观"
        style="width: 10rem" />
      <div 
        v-show="active ? lives.length > 0 : list.length > 0" 
        class="videos__link">
        提醒我
      </div>
    </footer>
  </div>
</template>
<script>
import ActBtn from './act-btn.vue'

export default {
  components: {
    ActBtn
  },
  data () {
    return {
      active: true,
      block: true,
      index: 0,
      listIndex: 0,
      video: [],
      lives: [
        {
          poster: require('../imgs/video.jpg'),
          date: '7月18日',
          time: '16:00',
          leftEN: 'Nova eSports',
          leftZH: '德国',
          rightEN: 'AG.Y',
          rightZH: '中国'
        }, {
          poster: require('../imgs/default.jpg'),
          date: '7月19日',
          time: '19:00',
          leftEN: 'Novts',
          leftZH: '美国',
          rightEN: 'JP',
          rightZH: '日本'
        }, {
          poster: require('../imgs/video.jpg'),
          date: '7月22日',
          time: '22:00',
          leftEN: '22',
          leftZH: '22',
          rightEN: '22',
          rightZH: '22'
        }
      ],
      list: [
        {
          poster: require('../imgs/default.jpg'),
          date: '7月18日',
          time: '16:00',
          leftEN: 'Nova eSports',
          leftZH: '德国',
          rightEN: 'AG.Y',
          rightZH: '中国'
        }, {
          poster: require('../imgs/video.jpg'),
          date: '9月99日',
          time: '99:00',
          leftEN: 'Novts',
          leftZH: '巴西',
          rightEN: 'kr',
          rightZH: '韩国'
        }, {
          poster: require('../imgs/default.jpg'),
          date: '9月22日',
          time: '29:00',
          leftEN: 'asf',
          leftZH: 'G胖',
          rightEN: 'cocos',
          rightZH: '刚体'
        }
      ]
    }
  },
  mounted () {
    this.$nextTick(function () {
      if (this.lives.length > 0) {
        this.video = this.lives[0]
        this.index = 0
      }
    })
  },
  methods: {
    pre () {
      if (this.index != 0) {
        this.index--
        this.video = this.lives[this.index]
      }
    },
    next () {
      if (this.index != this.lives.length - 1) {
        this.index++
        this.video = this.lives[this.index]
      }
    },
    listPre () {
      if (this.listIndex != 0) {
        this.listIndex--
        this.video = this.list[this.listIndex]
      }
    },
    listNext () {
      if (this.listIndex != this.list.length - 1) {
        this.listIndex++
        this.video = this.list[this.listIndex]
      }
    },
    toLive () {
      if (!this.active && this.lives.length > 0) {
        this.video = this.lives[0]
      }
      this.index = 0
      this.active = true
    },
    toList () {
      if (this.active && this.list.length > 0) {
        this.video = this.list[0]
      }
      this.listIndex = 0
      this.active = false
    }
  }
}
</script>
