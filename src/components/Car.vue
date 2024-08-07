<template>
    <div class="car">
        <h1>一辆{{ car.brand }}，价格{{ car.price }}万</h1>
        <button @click="changePrice">修改价格</button>
        <li v-for="c in cars" :key="c.brand">一辆{{ c.brand }}，价格{{ c.price }}万</li>
        <button @click="changeFirstPrice">修改第一个价格</button>
    </div>
</template>

<script>
export default {
    name: 'Car'
}
</script>

<script setup>
import { reactive } from 'vue'
let car = reactive({ brand: '奔驰', price: 100 })
let cars = reactive([{ brand: '奔驰', price: 100 },
{ brand: '三菱', price: 90 }
])

function changePrice() {
    car.price += 10;
}

function changeFirstPrice() {
    cars[0].price += 10;
}

function changeCar() {
    // 页面引用不随变量引用变化，故不生效
    // car = { brand: '三菱', price: 90 }
    // car = reactive({ brand: '三菱', price: 90 })
    Object.assign(car,{ brand: '三菱', price: 90 })
}
</script>