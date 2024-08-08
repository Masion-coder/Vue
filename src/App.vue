<template>
    <h1 ref="title">6789</h1>
    <button @click="show">bbb</button>
    <Person ref="person"/>
    <button @click="showPerson">人</button>
</template>
<script>
export default {
    name: 'App'
}
</script>
<script setup>
import Car from './components/Car.vue';
import Person from './components/Person.vue';
import Watch from './components/Watch.vue';
import WatchEffect from './components/WatchEffect.vue';
import { ref } from 'vue'

let title = ref()
let person = ref()

function show() {
    console.log(title.value)
}

function showPerson() {
    // 返回组件实例
    console.log(person.value)
}

</script>

<style></style>