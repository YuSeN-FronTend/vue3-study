<template>
    <div class="grandSon">
        <h3>我是GrandSon组件</h3>
        <DialogVue/>
    </div>
</template>

<script>
import DialogVue from './Dialog.vue';
export default {
    name: 'GrandSon',
    components:{
        DialogVue
    }
}
</script>

<style scoped>
.grandSon {
    background-color: orange;
    padding: 10px;
}
</style>