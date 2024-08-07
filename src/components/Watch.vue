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
import { ref, watch } from 'vue'

let person = ref ({name:'张三',age:18})

function changeName() {
    person.value.name += '~'
}

function changeAge() {
    person.value.age++
}

function changePerson() {
    person.value = {name:'李四',age:40}
}
// // 监视对象类型，监视对象地址
// watch(person,(newValue,oldValue)=>{console.log('person改变了',newValue,oldValue)})

watch(person,(newValue,oldValue)=>{console.log('person改变了',newValue,oldValue)},{deep:true})

</script>