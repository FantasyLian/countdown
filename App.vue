<template>
    <div id="app">
        <h1>短信验证码</h1>
		<count-down></count-down> 
        <br>
        <br>
        <count-down-two></count-down-two> 
    </div>
</template>
<script>
import CountDown from './components/CountDown.vue';
import CountDownTwo from './components/CountDown2.vue';
export default {
    name: 'app',
    components: { CountDown, CountDownTwo },
    data() {
        return {
            
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