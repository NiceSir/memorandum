<template>
    <div>{{ messageBoxOptions.message }}</div>
    <el-button @click="messageBoxOptions.message++">+1</el-button>
</template>

<script setup>
import { ElMessageBox } from 'element-plus'
import { reactive,getCurrentInstance, h } from 'vue';
const { appContext } = getCurrentInstance()
const messageBoxOptions=reactive({
    message:10
})
console.log(appContext,'appContext');

const interval=setInterval(()=>{
    if(messageBoxOptions.message===0){
        console.log('倒计时结束');
        clearInterval(interval)
        return
    }
    
    messageBoxOptions.message--
},1000)


const elMessage=ElMessageBox
console.log(elMessage,'elMessage');

elMessage.alert(()=>{return h('div',messageBoxOptions.message)},"title",{})
console.log(appContext,'appContext11');
</script>

<style lang='less' scoped>

</style>