<script>
    import { reactive, ref } from '@vue/reactivity'
    import child from '../child.vue'

    const msg = ref('')

    const updateHandler = (data) => {
        console.log(data)
    }
</script>

<template>

    <input type="text" v-model="msg" />
    <br />
    <child v-bind:data="msg" @update="updateHandler"/>
    
</template>

<style scoped>

</style>
