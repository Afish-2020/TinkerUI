<template>
    <h1 class="switch-title">Input 组件</h1>
    <!-- <Demo :component="Button1Demo" /> -->
    <h3 class="switch-h">基础用法</h3>
    <P>
        绑定
        <strong class="switch-p">v-model</strong> 到一个
        <strong class="switch-p">String</strong> 类型的变量,添加
        <strong class="switch-p">pattern</strong> 到一个
        <strong class="switch-p">Boolen</strong> 类型的变量。
    </P>
    <Demo :component="Input1Demo" />
    <h3 class="switch-h">支持类型</h3>
    <P>
        添加
        <strong class="switch-p">type</strong> 属性来定义输入框的类型，默认为文本类型。
    </P>
    <Demo :component="Input3Demo" />
    <h3 class="switch-h">支持 disabled</h3>
    <P>
        添加
        <strong class="switch-p">disabled</strong> 属性来定义输入框是否被禁用。
    </P>
    <Demo :component="Input2Demo" />
</template>
<script>
import Input1Demo from "./Input1.demo.vue";
import Input2Demo from "./Input2.demo.vue";
import Input3Demo from "./Input3.demo.vue";
import Demo from './Demo.vue'
export default {
    components: { Demo },
    setup() {
        return { Input1Demo, Input2Demo, Input3Demo }
    }
}
</script>