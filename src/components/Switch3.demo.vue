<demo>
文字描述
</demo>

<template>
    <Switch v-model:value="bool" activeText="是" inactiveText="否" />
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
