<template>
    <h4>当前的x.y值是: {{ x.y }}</h4>
    <button @click="x.y++">点我x+1</button>
    <hr>
    <h4>{{ person }}</h4>
    <h2>姓名：{{ name }}</h2>
    <h2>年龄：{{ age }}</h2>
    <h2>薪水：{{ job.j1.salary }}K</h2>
    <button @click="name += '~'">修改姓名</button>
    <button @click="age++">修改年龄</button>
    <button @click="job.j1.salary++">涨薪</button>
</template>

<script>
import {reactive, ref , toRefs, shallowReactive, shallowRef} from 'vue';
export default {
    name: 'Demo',
    setup() {
        // let person = shallowReactive({ // 只考虑第一层数据的响应式
        let person = reactive({
            name: '于森',
            age: 18,
            job: {
                j1: {
                    salary: 20
                }
            }
        })
        // let x = shallowRef({  // 对象或数组无法响应式
        let x = ref ({
            y:0
        });
        return {
            person, 
            x,
            ...toRefs(person)
        }
    }
}
</script>

