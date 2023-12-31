<template>
  <div class="countdown" @click="fn">
    <a>{{ context }}</a>
  </div>
</template>
<script>
export default {
  name: 'countDown',
  props: ['deftext', 'second', 'fn'],
  data () {
    return {
      time: 0,
      timer: null,
      canClick: true
    }
  },
  destroyed () {
    clearInterval(this.timer)
    this.timer = null
    console.log('定时器已销毁')
  },
  computed: {
    context () {
      return this.time > 0 ? this.time + '秒' : this.deftext
    }
  },
  methods: {
    countDown () {
      if (!this.canClick) return
      this.time = this.second
      this.canClick = false
      this.timer = setInterval(() => {
        this.time--
        if (this.time < 0) {
          clearInterval(this.timer)
          this.canClick = true
        }
      }, 1000)
    },
    stopCount () {
      clearInterval(this.timer)
      this.timer = null
      console.log('计时器停止')
    }
  }
}
</script>
<style lang="less">
.countdown {
  display: inline;

  a {
    width: 110px;
    height: 32px;
    font-size: 14px;
    font-weight: 400;
    color: rgba(24, 144, 255, 1);
    line-height: 32px;
  }
}
</style>
