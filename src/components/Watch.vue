<template>
    <div>
        <h1>姓名：{{ person.name }}</h1>
        <h1>年龄：{{ person.age }}</h1>
        <h1>汽车：{{ person.car.c1 }}, {{ person.car.c2 }}</h1>
        <button @click="changeName">修改名字</button> <br>
        <button @click="changeAge">修改年龄</button> <br>
        <button @click="changeC1">修改汽车1</button> <br>
        <button @click="changeC2">修改汽车2</button> <br>
        <button @click="changeCar">修改汽车</button>
    </div>
</template>

<script>
export default {
    name: 'Watch'
}
</script>

<script setup>
import { reactive, watch } from 'vue'
let person = reactive({
    name: '张三',
    age: 18,
    car: {
        c1: '奔驰',
        c2: '宝马'
    }
})
function changeName() {
    person.name += '~'
}
function changeAge() {
    person.age++
}
function changeC1() {
    person.car.c1 = '雅迪'
}
function changeC2() {
    person.car.c2 = '大众'
}
function changeCar() {
    person.car = {c1: '奔驰', c2: '宝马'}
}


watch(()=>[person.name, person.car.c1], (newValue, oldValue)=>{console.log('person变化了',newValue, oldValue)})

</script>