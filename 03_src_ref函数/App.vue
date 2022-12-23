<template>
  <h1>一个人的信息</h1>
  <h2>姓名： {{name}}</h2>
  <h2>年龄：{{age}}</h2>
  <h2>{{ job }}</h2>
  <button @click="changeInfo">修改人的信息</button>
</template>

<script>
import {ref} from 'vue';
export default {
  name: 'App',
  setup() {
    // 数据
    let name = ref("于s");
    let age = ref(18);
    let job = ref({
      type: '前端工程师',
      salary: '30K'
    })

    // 方法
    function changeInfo() {
      name.value = 'yu森';
      age.value = 23;
      job.value.type = '前端高级工程师'
      console.log(job.value);
    }
    return {
      name,
      age,
      changeInfo,
      job
    }
  }
}
</script>

