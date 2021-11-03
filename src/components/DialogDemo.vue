<template>
    <h1 class="switch-title">Dialog 组件</h1>
    <h3 class="switch-h">基础用法</h3>
    <P>
        绑定
        <strong class="switch-p">v-model</strong> 到一个
        <strong class="switch-p">Boolean</strong> 类型的变量。
    </P>
    <Demo :component="Dialog3Demo" />
    <h3 class="switch-h">支持 closeOnClickOverlay</h3>
    <P>
        添加
        <strong class="switch-p">closeOnClickOverlay</strong> 设置是否通过点击遮罩层关闭
        <strong class="switch-p">Dialog</strong>。
    </P>
    <Demo :component="Dialog4Demo" />
    <h3 class="switch-h">支持处理 Button</h3>
    <P>
        添加处理
        <strong class="switch-p">Button</strong> 对
        <strong class="switch-p">Dialog</strong> 进行下一步处理。
    </P>
    <Demo :component="Dialog1Demo" />
    <h3 class="switch-h">支持函数式调用</h3>
    <p>隐藏dom结构，只暴露出调用的api</p>
    <Demo :component="Dialog2Demo" />
</template>
<script lang="ts">
import Dialog1Demo from "./Dialog1.demo.vue"
import Dialog2Demo from "./Dialog2.demo.vue"
import Dialog3Demo from "./Dialog3.demo.vue"
import Dialog4Demo from "./Dialog4.demo.vue"
import Demo from './Demo.vue'
export default {
    components: { Demo },
    setup() {
        return { Dialog1Demo, Dialog2Demo, Dialog3Demo, Dialog4Demo }
    }
}
</script>
<style>
</style>