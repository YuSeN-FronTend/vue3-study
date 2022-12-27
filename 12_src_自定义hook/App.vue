<template>
  <button @click="isShowDemo = !isShowDemo">切换隐藏Demo</button>
  <DemoVue v-if="isShowDemo">
  </DemoVue>
  <hr>
  <TestVue></TestVue>
</template>

<script>
import DemoVue from './components/Demo.vue';
import TestVue from './components/Test.vue';
import { ref } from 'vue';
export default {
  name: 'App',
  components:{
    DemoVue,
    TestVue
  },
  setup() {
    let isShowDemo = ref(true);
    return {
      isShowDemo
    }
  }
}
</script>

