<template>
    <div>
        <li v-for="person in list" :key="person.id">{{ person.name }}--{{ person.age }}</li>
    </div>
</template>

<script lang="ts">
export default {
    name: 'Person',
}
</script>

<script lang="ts" setup>
import { PersonInter } from '@/types';

// // 接收
// defineProps(['list'])

// // 接收+限制类型
// defineProps<{list: PersonInter[]}>()

// 接收+限制类型+限制必要性+指定默认值
let x = withDefaults(defineProps<{list: PersonInter[],tmp?:string}>(),
{list:()=>[{id: '123', name: '张三', age: 10}]})
</script>