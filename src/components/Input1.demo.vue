<demo>
常规用法
</demo>

<template>
    <div>
        <Input v-model:value="text" placeholder="请输入内容" pattern="true" />
    </div>
</template>
<script>
import { ref } from 'vue'
import Input from "../lib/Input.vue"
export default {
    setup() {
        const text = ref('')
        return { Input, text }
    }
}
</script>