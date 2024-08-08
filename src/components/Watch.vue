<template>
    <div>
        <h1>姓名：{{ person.name }}</h1>
        <h1>年龄：{{ person.age }}</h1>
        <h1>汽车：{{ person.car.c1 }}, {{ person.car.c2 }}</h1>
        <buttion @click="changeName">修改名字</buttion> <br>
        <buttion @click="changeAge">修改年龄</buttion> <br>
        <buttion @click="changeC1">修改汽车1</buttion> <br>
        <buttion @click="changeC2">修改汽车2</buttion> <br>
        <buttion @click="changeCar">修改汽车</buttion>
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

// 监视响应式对象中的某个属性，且该属性是基本类型，要用getter函数式
watch(()=>{return person.name}, (newValue, oldValue)=>{console.log('person.name变化了', newValue, oldValue)})
// car地址变化不能监视
watch(person.car, (newValue, oldValue)=>{console.log('person.car变化了（内容）',newValue, oldValue)})
// car属性变化不能监视
watch(()=>person.car, (newValue, oldValue)=>{console.log('person.car变化了（地址）',newValue, oldValue)})

watch(()=>person.car, (newValue, oldValue)=>{console.log('person.car变化了',newValue, oldValue)}, {deep: true})

</script>