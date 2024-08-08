<template>
    <div class="person">
        <h1 ref="title">123456</h1>
        <button @click="show">aaa</button>
    </div>
</template>

<script>
export default {
    name: 'Person',
}
</script>

<script setup>
import { ref } from 'vue'

let title = ref()

function show() {
    console.log(title.value)
}

</script>