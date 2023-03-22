<script setup>
    import { reactive, ref } from '@vue/reactivity'
    import { computed, watch } from '@vue/runtime-core'

    const msgCount = computed(() => {
        return props.data.length
    })

    // defineProps(['data'])

    const props = defineProps({
        data: {
            type: String,
            default: '',
        },
    })

    const emit = defineEmits(['update'])

    watch(msgCount,(newValue) => {
        emit('update',`from child: ${newValue}`)
    })

</script>

<template>

    <div>
        字數:{{ msgCount }}
        <!-- {{ data }} -->
    </div>
  
</template>

<style scoped>

</style>
