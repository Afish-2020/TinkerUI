<template>
    <h1 class="switch-title">Tabs 组件</h1>
    <h3 class="switch-h">基础用法</h3>
    <Demo :component="Tabs1Demo" />
</template>
<script>
import Demo from './Demo.vue'
import Tabs1Demo from './Tabs1.demo.vue'
export default {
    components: { Demo },
    setup() {
        return { Tabs1Demo }
    }
}
</script>