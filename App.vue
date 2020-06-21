<template>
    <div id="app">
        <h1>短信验证码</h1>
		<count-down></count-down> 
    </div>
</template>
<script>
import CountDown from './components/CountDown.vue';
export default {
    name: 'app',
    components: { CountDown },
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