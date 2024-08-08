<template>
    <div>
        <h1>当前温度{{ temp }}℃</h1>
        <h1>当前水位{{ height }}cm</h1>
        <button @click="changeTemp">水温+10</button> <br>
        <button @click="changeHeight">水位+5</button>
    </div>
</template>

<script>
export default {
    name: 'WatchEffect'
}
</script>

<script setup>
import { ref, watchEffect } from 'vue'

let temp = ref(10)
let height = ref(0)

function changeTemp() {
    temp.value += 10
}

function changeHeight() {
    height.value += 5
}

watchEffect(()=>{
    if (temp.value >= 60 || height.value >= 80) console.log('发送信息')
})

</script>