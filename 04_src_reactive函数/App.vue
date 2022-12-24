<template>
  <h1>一个人的信息</h1>
  <h2 v-show="person.name">姓名： {{person.name}}</h2>
  <h2>{{ person.job }}</h2> 
  <h2>年龄：{{person.age}}</h2>
  <h2>性别：{{person.sex}}</h2>
  <button @click="changeInfo">修改人的信息</button>
  <button @click="addSex">添加一个sex属性</button>
  <button @click="deleteName">删除一个name属性</button>
</template>

<script>
import {ref, reactive} from 'vue';
export default {
  name: 'App',
  setup() {
    // 数据
    // let name = ref("于s");
    // let age = ref(18);
    // let job = reactive({
    //   type: '前端工程师',
    //   salary: '30K'
    // })
    // let hobby = reactive(['抽烟','喝酒','烫头']);
    let person = reactive({
      name: '于s',
      age:18,
      job:{
        type: '前端工程师',
        salary: '30K'
      },
      hobby: ['抽烟', '喝酒', '烫头']
    })

    // 方法
    function changeInfo() {
      person.name = 'yu森';
      person.age = 23;
      person.job.type = '前端高级工程师';
      person.hobby[0] = '学习';
      console.log(person.job);
    }

    function addSex() {
      person.sex = '男';
    }
    function deleteName() {
      delete person.name;
    }

    return {
      person,
      changeInfo,
      addSex,
      deleteName
    }
  }
}
</script>

