<template>
  <div>
    <button type="button" v-show="show" @click="getCode">获取验证码</button>
    <button type="button" v-show="!show">{{ count }} 秒</button>
  </div>
</template>
<script>
export default {
  name: 'countdown',
  data () {
    return {
      show: true,
      count: '',
      timer: null
    }
  },
  created () {

  },
  destroyed () {
    clearInterval(this.timer)
    this.timer = null
    console.log('定时器已销毁')
  },
  methods: {
    getCode () {
      const TIME_COUNT = 60
      if (!this.timer) {
        this.count = TIME_COUNT
        this.show = false
        this.timer = setInterval(() => {
          if (this.count > 0 && this.count <= TIME_COUNT) {
            this.count--
          } else {
            this.show = true
            clearInterval(this.timer)
            this.timer = null
          }
        }, 1000)
      }
    }
  }
}
</script>