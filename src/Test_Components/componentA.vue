<script setup>

    import { ref } from '@vue/reactivity ';
    
    const data = "Hello Vue"
    const text = ref("123fd") // reference
    const view = ref(1)

    const changeView = (index) => {
        view.value = index
    }
    const dataList = {
        key1:'a',
        key2:'b',
        key3:'c',
        key4:'d'
    }

    const test = ref('test')

    setTimeout( () => {
        test.value='test again'
    },2000)
    
    
    //test.value='test again'
    
</script>


<template>
<button v-on:click="changeView(1)">顯示單向綁定</button>
<button @click="changeView(2)">顯示雙向綁定</button>
<button @click="changeView(9)">沒畫面</button>
    

    <div class="container-1" v-if="view === 1" >
        <p>資料單向綁定</p>
        {{data}}
    </div>
    
    <div class="container-2" v-else-if="view === 2">
        <p>資料雙向綁定</p>
        <input type="text" v-model="text"/> 
        <p>{{text}}</p>
    </div>
    
    <div v-else>
        <h4>沒畫面</h4>
    </div>

    <div>
        <p 
            v-for = "(value,key,index) in dataList"
            :key = "value" 
        >
            <span class="hint" v-show="key !== 'key3'">
                {{index}}. {{key}}: {{value}}
            </span>
        </p>
    </div>

    <div> 
        <p
            class="test-cls"
            :key = "test" 
        > {{test}}</p> <!-- :key = "test" -> 重新渲染 -->
    </div>
</template>


<style scoped>
.container-1{
    border: 2px red solid;
}
.container-2{
    border: 2px skyblue  solid;
}

.test-cls{
    font-size: 40px;
    animation: openIn 1s ease-in-out;
}
@keyframes openIn{
    0%{
        opacity: 0;
        transform: translateY(20px);
    }
    100%{
        opacity: 1;
        transform: translateY(0);
    }
}
</style>
