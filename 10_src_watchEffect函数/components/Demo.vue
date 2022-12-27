<template>
    <h2>当前求和为：{{ sum }}</h2>
    <button @click="sum++">点我加一</button>
    <br>
    <h2>当前的信息为：{{ msg }}</h2>
    <button @click="msg+='!'">修改当前信息 </button>
    <hr>
    <h2>姓名：{{ person.name }}</h2>
    <h2>年龄：{{ person.age }}</h2>
    <h2>薪水：{{ person.job.j1.salary }}</h2>
    <button @click="person.name+='~'">修改姓名</button>
    <button @click="person.age++">修改年龄</button>
    <button @click="person.job.j1.salary++">涨薪</button>
</template>

<script>
import {ref,reactive, watch, watchEffect} from 'vue';
export default {
    name: 'Demo',
    setup() {
        let sum = ref(0);
        let msg = ref('你好a');
        let person = reactive({
            name: '于森',
            age: 18,
            job:{
                j1:{
                    salary: 20
                }
            }
        })
        // 监视
        // watch(sum,(newValue, oldValue) => {
        //     console.log('sum修改了', newValue, oldValue);
        // },{immediate:true})

        //  
        watchEffect(() => {
            const x1 = sum.value;
            const x2  = person.job.j1.salary
            console.log('watchEffect所指定的回调执行了');
        })
        return {
            sum,
            msg,
            person
        }
    }
}
</script>

