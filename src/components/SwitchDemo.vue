<template>
    <div>
        <h1 class="switch-title">Switch 组件</h1>
        <h3 class="switch-h">基础用法</h3>
        <P>
            绑定
            <strong class="switch-p">v-model</strong> 到一个
            <strong class="switch-p">Boolean</strong> 类型的变量。
        </P>
        <Demo :component="Switch1Demo" />
        <h3 class="switch-h">文字描述</h3>
        <p>
            使用
            <strong class="switch-p">active-text</strong> 属性与
            <strong class="switch-p">inactive-text</strong> 属性来设置开关的文字描述。
        </p>
        <Demo :component="Switch3Demo" />
        <h3 class="switch-h">支持 disabled</h3>
        <p>
            设置
            <strong class="switch-p">disabled</strong> 属性来控制是否禁用开关。
        </p>
        <Demo :component="Switch2Demo" />
    </div>
</template>
<script lang="ts">
import Demo from './Demo.vue'
import Switch1Demo from "./Switch1.demo.vue"
import Switch2Demo from "./Switch2.demo.vue"
import Switch3Demo from "./Switch3.demo.vue"
import { ref } from 'vue'
export default {
    components: {
        Demo
    },
    setup() {
        const bool = ref(false)
        return { bool, Switch1Demo, Switch2Demo, Switch3Demo }
    }
}
</script>