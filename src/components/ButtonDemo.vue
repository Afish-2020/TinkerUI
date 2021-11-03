<template>
    <h1 class="switch-title">Button 组件</h1>
    <!-- <Demo :component="Button1Demo" /> -->
    <h3 class="switch-h">基础用法</h3>
    <P>
        使用
        <strong class="switch-p">theme、level</strong> 来定义按钮的样式。
    </P>
    <Demo :component="Button3Demo" />
    <h3 class="switch-h">支持 size</h3>
    <P>
        使用
        <strong class="switch-p">size</strong> 来设置不同的按钮尺寸，可供选择的尺寸有：
        <strong class="switch-p">big、normal、small</strong>。
    </P>
    <Demo :component="Button2Demo" />
    <h3 class="switch-h">支持 disabled</h3>
    <P>
        添加
        <strong class="switch-p">disabled</strong> 属性来定义按钮是否被禁用。
    </P>
    <Demo :component="Button4Demo" />
    <h3 class="switch-h">支持 loading</h3>
    <p>
        添加
        <strong class="switch-p">loading</strong> 属性设置组件在加载中。
    </p>
    <Demo :component="Button5Demo" />
</template>
<script lang="ts">
import Button1Demo from "./Button1.demo.vue";
import Button2Demo from "./Button2.demo.vue";
import Button3Demo from "./Button3.demo.vue";
import Button4Demo from "./Button4.demo.vue";
import Button5Demo from "./Button5.demo.vue";
import Demo from './Demo.vue'
export default {
    components: { Demo },
    setup() {
        return {
            Button1Demo,
            Button2Demo,
            Button3Demo,
            Button4Demo,
            Button5Demo
        }
    }
}
</script>