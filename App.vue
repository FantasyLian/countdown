<template>
    <div id="app">
        <h1>短信验证码</h1>
		<count-down></count-down> 
        <br>
        <br>
        <count-down-two></count-down-two>
        <br>
        <br>
        <count-down-third :fn="getAdminVerifyCode" :deftext="'获取验证码'" ref="child" :second="60" />
    </div>
</template>
<script>
import CountDown from './components/countdown.vue';
import CountDownTwo from './components/countdown2.vue';
import CountDownThird from './components/countdown3.vue';
export default {
    name: 'app',
    components: { CountDown, CountDownTwo, CountDownThird },
    data() {
        return {
            
        }
    },
    methods: {
        getAdminVerifyCode() {
            this.$refs.child.countDown()
        }
    }
}
</script>
<style lang="css">
    #app {
        font-family: "Avenir", Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>