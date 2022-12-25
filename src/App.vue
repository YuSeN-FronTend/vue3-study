<template>
  <DemoVue @hello="showHelloMsg" msg="ys">
    <template v-slot:qwe>
    <span>于森</span>
    </template>
    <template v-slot:asd>
      <span>于森</span>
    </template>
  </DemoVue>
</template>

<script>
import DemoVue from './components/Demo.vue';
export default {
  name: 'App',
  components:{
    DemoVue
  },
  setup() {
    function showHelloMsg(value) {
      alert(`你好，我收到参数${value}`)
    }
    return {
      showHelloMsg
    }
  }
}
</script>

