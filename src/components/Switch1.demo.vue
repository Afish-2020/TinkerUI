<demo>
常规用法
<p>绑定 v-model 到一个 Boolean 类型的变量。 可以使用 active-color 属性与 inactive-color 属性来设置开关的背景色。</p>
</demo>

<template>
    <Switch v-model:value="bool" />
</template>
<script lang="ts">
import { ref } from 'vue'
import Switch from "../lib/Switch.vue"
export default {
    components: {
        Switch
    },
    setup() {
        const bool = ref(true)
        return { bool }
    }
}
</script>
