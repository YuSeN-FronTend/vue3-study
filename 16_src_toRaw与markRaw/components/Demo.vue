<template>
    <h4>当前的求和为： {{ sum }}</h4>
    <button @click="sum++">点我++</button>
    <hr>
    <h2>姓名：{{ name }}</h2>
    <h2>年龄：{{ age }}</h2>
    <h2>薪水：{{ job.j1.salary }}K</h2>
    <h2 v-show="person.car">座驾信息: {{ person.car }}</h2>    
    <button @click="name += '~'">修改姓名</button>
    <button @click="age++">修改年龄</button>
    <button @click="job.j1.salary++">涨薪</button>
    <button @click="showRowPerson">输出最原始的person</button>
    <button @click="addCar">给人添加一台车</button>
    <button v-show="person.car" @click="person.car.name='劳斯莱斯'">换车名</button>
    <button v-show="person.car" @click="changePrice">换价格</button>
</template>

<script>
import {reactive, ref , toRefs, toRaw, markRaw} from 'vue';
export default {
    name: 'Demo',
    setup() {
        let sum = ref(0);
        let person = reactive({
            name: '于森',
            age: 18,
            job: {
                j1: {
                    salary: 20
                }
            }
        })

        function showRowPerson() {
            person = toRaw(person);
            console.log(person);

            // 行不通
            // const s = toRaw(sum);
            // console.log(s);
        }

        function addCar() {
            let car = {
                name: '奔驰',
                price: 40
            }
            person.car = markRaw(car)
        }

        function changePrice() {
            person.car.price++;
            console.log(person.car.price);
        }

        return {
            person, 
            sum,
            showRowPerson,
            addCar,
            changePrice,
            ...toRefs(person)
        }
    }
}
</script>

