<script setup>
    import { computed,ref } from 'vue';

    const num = ref(1)
    const firstName = ref('John')
    const lastName = ref('Doe')

    const numFormat = computed(() => {
        if(Number.isNaN(num.value * 100)) return num   
        return `${num.value * 100}%` 
    })

    const fullName = computed({
        get(){
            return `${firstName.value} ${lastName.value}`
        },

        set(newName){
            const [newFirstName , newLastName] = newName.split(' ')

            firstName.value = newFirstName
            lastName.value = newLastName

        }
    })

</script>

<template>

    <h1>Computed</h1>

    <input type="number" v-model="num" />
    <br /><br />
    <input type="text" v-model="fullName" />
    <p> {{ firstName }}</p>
    <br />
    {{ lastName}}

    <h3>{{ numFormat }}</h3>

</template>

<style scoped>

</style>
 