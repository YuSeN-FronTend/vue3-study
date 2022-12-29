<template>
    <div>
        <button @click="showDialog = true">点我弹个窗</button>
        <teleport to='body'>
            <div v-show="showDialog"  class="mark">
                <div class="dialog">
                    <h3>我是一个弹窗</h3>
                    <h4>一些内容</h4>
                    <h4>一些内容</h4>
                    <h4>一些内容</h4>
                    <button @click="showDialog = false">关闭弹窗</button>
                </div>
            </div>
        </teleport>
    </div>
</template>

<script>
import { ref } from 'vue';

    export default {
        name: 'Dialog',
        setup() {
            let showDialog = ref(false);
            return {
                showDialog
            }
        }
    }
</script>

<style scoped>
.mark{
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.5);
}
.dialog{
    text-align: center;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    /*margin-top: -150px;
    margin-left: -150px;*/
    width: 300px;
    height: 300px;
    
    background-color: green;
}
</style>