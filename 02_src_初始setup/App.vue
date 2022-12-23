<template>
  <h1>一个人的信息</h1>
  <h2>姓名： {{name}}</h2>
  <h2>年龄：{{age}}</h2>
  <h2>性别: {{ sex }}</h2>
  <h2>{{ a }}</h2>
  <button @click="sayHello">说话</button>
  <button @click="sayWelcome">vue2中的方法</button>
  <button @click="test">测试在vue2方法中调用vue3语法中的数据</button>
  <br>
  <br>
  <button @click="test2">测试在vue3方法中调用vue2语法中的数据</button>
</template>

<script>
// import {h} from 'vue';
export default {
  name: 'App',
  data(){
    return {
      sex: '男',
      a: 20,
    }
  },
  methods:{
    sayWelcome() {
      alert('欢迎回到vue2')
    },
    test() {
      console.log(this.sex);
      console.log(this.name);
      console.log(this.age);
      this.sayHello();
    }
  },
  // 此处只是测试一下setup，暂时不考虑响应式的问题
  setup() {
    // 数据
    let name = "于s";
    let age = 18;
    let a = 15;
    // 方法
    function sayHello() {
      console.log(`我叫${name}, 我${age}, 你好啊！`);
    }
    function test2() {
      console.log(this.sex);
      console.log(this.sayWelcome);
    }
    return {
      name,
      age,
      sayHello,
      test2,
      a
    }
    // return ()=> h('div', 'yusen')
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
