<template>
    <div class="child">
        <h3>我是Child组件</h3>
        <grandSon/>
    </div>
</template>

<script>
import grandSon from '@/components/grandSon'
export default {
    name: 'Child',
    components: {
        grandSon
    }
}
</script>

<style scoped>
.child {
    background-color: skyblue;
    padding: 10px;
}
</style>