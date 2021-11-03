<demo>
常规用法
</demo>

<template>
    <Tabs v-model:selected="x">
        <Tab title="吃饭">吃饭</Tab>
        <Tab title="睡觉">睡觉</Tab>
        <Tab title="看电影">看电影</Tab>
    </Tabs>
</template>
<script lang="ts">
import { ref } from 'vue'
import Tab from "../lib/Tab.vue"
import Tabs from "../lib/Tabs.vue"
export default {
    components: { Tab, Tabs },
    setup() {
        const x = ref("吃饭")
        return { x }
    }
}
</script>
