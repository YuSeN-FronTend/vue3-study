<template>
  <div class="app">
    <h3>我是App组件</h3>
    <Suspense>
      <template v-slot:default>
        <Child />
      </template>
      <template v-slot:fallback>
        <h3>稍等，加载中。。。</h3>
      </template>
    </Suspense>
  </div>
</template>

<script>
// import Child from './components/child' // 静态引入
  import { defineAsyncComponent } from 'vue'; 
  const Child = defineAsyncComponent(()=>import('./components/child.vue')) // 动态引入 也叫异步引入
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