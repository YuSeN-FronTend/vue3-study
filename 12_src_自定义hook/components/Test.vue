<template>
        <h2>我是Test组件</h2>
        <h3>x: {{ point.x }}, y: {{ point.y }}</h3>
</template>

<script>
import usePoint from '@/hooks/usePoint'
    export default{
        name: 'Test',
        setup() {
            let point = usePoint();
            return {point};
        }
    }
</script>