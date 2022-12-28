<template>
    <div class="grandSon">
        <h3>我是GrandSon组件(孙), {{ name }}--{{ price }}</h3>
    </div>
</template>

<script>
import { inject, toRefs} from 'vue';
export default {
    name: 'GrandSon',
    setup() {
        let car = inject('car');
        return {
            ...toRefs(car)
        }
    }

}
</script>

<style scoped>
.grandSon {
    background-color: orange;
    padding: 10px;
}
</style>