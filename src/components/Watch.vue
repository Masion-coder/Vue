<template>
    <div>
        <h1>姓名：{{ person.name }}</h1>
        <h1>年龄：{{ person.age }}</h1>
        <buttion @click="changeName">修改名字</buttion> <br>
        <buttion @click="changeAge">修改年龄</buttion> <br>
        <buttion @click="changePerson">修改人</buttion>
    </div>
</template>

<script>
export default {
    name: 'Watch'
}
</script>

<script setup>
import { reactive, watch } from 'vue'

let person = reactive({ name: '张三', age: 18 })

function changeName() {
    person.name += '~'
}

function changeAge() {
    person.age++
}

function changePerson() {
    Object.assign(person, { name: '李四', age: 40 })
}
// // 监视对象类型，监视对象地址
// watch(person,(newValue,oldValue)=>{console.log('person改变了',newValue,oldValue)})

// reactive默认开启深层监视
watch(person, (newValue, oldValue) => { console.log('person改变了', newValue, oldValue) })
</script>