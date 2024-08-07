<template>
    <div>
        <h1>计数器:{{ counter }}</h1>
        <buttion @click="changeCounter">点我+1</buttion>
    </div>
</template>

<script>
export default {
    name: 'Watch'
}
</script>

<script setup>
import { ref, watch } from 'vue'

let counter = ref(0)

function changeCounter() {
    counter.value++
}

// 监视,监视值+函数
const stop = watch(counter, (newValue, oldValue) => { console.log('counter变化了', newValue, oldValue);if(newValue >= 18) stop() })
</script>