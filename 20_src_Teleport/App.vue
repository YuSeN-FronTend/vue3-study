<template>
  <div class="app">
    <h3>我是App组件</h3>
    <Child/>
  </div>
</template>

<script>
import Child from './components/child'
  export default {
    name: 'App',
    components: {
      Child
    },
  }
</script>

<style scoped>
.app{
  background-color: gray;
  padding: 10px;
}
</style>