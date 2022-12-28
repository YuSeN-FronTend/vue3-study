<template>
  <div class="app">
    <h3>我是App组件(祖), {{ name }}--{{ price }}</h3>
    <Child/>
  </div>
</template>

<script>
import { reactive, toRefs, provide } from 'vue';
import Child from './components/child.vue'
  export default {
    name: 'App',
    components: {
      Child
    },
    setup() {
      let car = reactive({
        name: '劳斯莱斯',
        price: '400W'
      })
      provide('car',car); // 给自己的后代组件传递数据
      return {
        ...toRefs(car)
      }
    }
  }
</script>

<style scoped>
.app{
  background-color: gray;
  padding: 10px;
}
</style>