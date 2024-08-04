<template>
    <div class="person">
        <h1>姓名:{{ name }}</h1>
        <h1>年龄:{{ age }}</h1>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">查看联系方式</button>
    </div>
</template>

<script>
export default {
    name: 'Person',
    setup() {
        // 数据，不是响应式数据
        let name = 'Masion'
        let age = 18
        let tel = '12345678'

        function changeAge() {

        }

        function showTel() {
            alert(tel)
        }

        return { name, age, changeAge, showTel }
    }
}
</script>