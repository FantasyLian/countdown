<template>
  <div>
    <button @click="countDown">{{ context }}</button>
  </div>
</template>
<script>
export default {
  name: 'CountdownTwo',
  data () {
    return {
      context: '获取验证码',
      totalTime: 60,
      canClick: true
    }
  },
  destroyed () {
    clearInterval(this.timer)
    this.timer = null
    console.log('定时器已销毁')
  },
  methods: {
    countDown () {
      if (!this.canClick) return
      this.canClick = false
      this.context = this.totalTime + '秒后重选发送'
      const timer = setInterval(() => {
        this.totalTime--
        this.context = this.totalTime + '秒后重选发送'
        if (this.totalTime < 0) {
          clearInterval(timer)
          this.context = '重新发送验证码'
          this.totalTime = 60
          this.canClick = true
        }
      }, 1000)
    }
  }
}
</script>
