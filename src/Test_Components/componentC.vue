<script setup>

    import { reactive, ref } from '@vue/reactivity'
    import { watch, watchEffect } from '@vue/runtime-core'

    // const text = ref({
    //     levels:{
    //         text:"",
    //     },
    // })

    // const text = reactive({
    //     levels:{
    //         text:"",
    //     },
    // }) //reactive 只能是一個物件

    const text = ref(' ')

    // watch(
    //     () => text.levels.text,
    //     (newData, oldData)=> {
    //     console.log(newData , oldData)
    // },{deep:true}
    // )

    // const stop = watchEffect( () =>{
    //     console.log(text.levels.text)
    //     if (text.levels.text === 'stop') stop()
    // })



    const dynamicStyle = reactive({
        color:'red',
        fontSize:'14px',
        Transition:'ease-in-out 0.2s'  
    })

    watch(text,(newData) => {

        if(newData.length % 2 === 0){
            dynamicStyle.color = 'skyblue'
            dynamicStyle.fontSize = '20px'
        }
        else{
            dynamicStyle.color = 'red'
            dynamicStyle.fontSize = '14px'
        }
    })

</script>

<template>

    <h3>Watch 監聽</h3>

    <input type="text" :style="dynamicStyle" v-model="text" />
    
    

</template>

<style scoped>

</style>
