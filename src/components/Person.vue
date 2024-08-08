<template>
    <div>
    </div>
</template>

<script lang="ts">
export default {
    name: 'Person',
}
</script>

<script lang="ts" setup>
import { PersonInter, PersonList } from '@/types'

let person: PersonInter = { id: '11', name: '11', age: 1 }

// let personList: Array<PersonInter> = [{ id: '11', name: '11', age: 1 }]
// let personList: PersonList = [{ id: '111', name: '11', age: 1 }]
let personList: PersonInter[] = [{ id: '111', name: '11', age: 1 }]
</script>