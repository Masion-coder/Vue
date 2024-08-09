<template>
    <Person :list="personList" />
</template>

<script lang="ts">
export default {
    name: 'App'
}
</script>

<script setup lang="ts">
import Person from './components/Person.vue';
import { PersonInter } from './types';
import { reactive } from 'vue'

let personList = reactive<PersonInter[]>([
    { id: '123', name: '张三', age: 10 },
    { id: '456', name: '李四', age: 20 },
    { id: '789', name: '王五', age: 30 }
])
</script>