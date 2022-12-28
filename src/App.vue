<template>
    <h3>我是App组件(祖)</h3>
</template>

<script>
import { reactive, readonly, ref, toRefs, isRef, isReactive, isReadonly, isProxy, markRaw, toRaw } from 'vue';
  export default {
    name: 'App',
    setup() {
      let car = reactive({
        name: '劳斯莱斯',
        price: '400W'
      });
      let sum = ref(0);
      let car2 = readonly(car);
      let car3 = toRaw(car)
      console.log(isRef(sum));
      console.log(isReadonly(car2));
      console.log(isReactive(car));
      console.log(isProxy(car3));
      console.log(isProxy(sum));
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