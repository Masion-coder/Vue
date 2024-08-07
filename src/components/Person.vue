<template>
    <div class="person">
        性：<input type="text" v-model="firstName"> <br>
        名：<input type="text" v-model="lastName"> <br>
        全名：<span>{{ fullName }}</span> <br>
        <button @click="changeFullName">修改全称</button>
    </div>
</template>

<script>
export default {
    name: 'Person',
}
</script>

<script setup>
import { ref, computed } from 'vue'

let firstName = ref('张')
let lastName = ref('三')

// // 计算属性，只读，不能改
// let fullName = computed(() => { return firstName.value + '-' + lastName.value })


let fullName = computed({
    get() {
        return firstName.value + '-' + lastName.value
    },
    set(val) {
        const [na1,na2] = val.split('-')
        firstName.value = na1
        lastName.value = na2
    }
})

function changeFullName() {
    fullName.value = 'li-si'
}
</script>