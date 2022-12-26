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
import {ref,reactive, watch} from 'vue';
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
        // 情况一：监视ref所定义的一个响应式数据
        // watch(sum, (newValue, oldValue) => {
        //     console.log('变化了', newValue, oldValue);
        // })
        // 情况二：监视ref所定义的多个响应式数据
        // watch([sum,msg],(newValue, oldValue)=>{
        //     console.log('sum或者msg变了',newValue,oldValue);
        // },{immediate:true})

        // 情况三：监视reactive所定义的一个响应式数据
        //     1.注意：此处无法正确获取oldValue
        //     2.注意：强制开启deep深度监听(deep配置无效)
        // watch(person, (newValue, oldValue) =>{
        //     console.log('person改变了', newValue, oldValue);
        // },{deep:false}) // 此处的deep配置无效

        // 情况四：监视reactive所定义的一个响应式数据中的某个属性
        // watch(() => person.age,(newValue, oldValue) => {
        //     console.log('person中的age被改变了', newValue,oldValue);
        // })

        // 情况四：监视reactive所定义的一个响应式数据中的某些属性
        // watch([() => person.age, () => person.name],(newValue, oldValue) => {
        //     console.log('person中的age和name被改变了', newValue,oldValue);
        // })

        // 特殊情况
        // watch([() => person.job], (newValue, oldValue) => {
        //     console.log('person中的job被改变了', newValue, oldValue);
        // }, {deep:true})  // 此处由于监视的是reactive定义的对象中的某个属性，所以deep配置有效

        return {
            sum,
            msg,
            person
        }
    }
}
</script>

