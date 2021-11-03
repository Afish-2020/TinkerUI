<demo>
常规用法
</demo>

<template>
    <Button @click="toggle" theme="link">打开Dialog</Button>
    <Dialog v-model:visible="x">
        <template v-slot:content>
            <span>这是一段信息</span>
        </template>
        <template v-slot:title>
            <span>提示</span>
        </template>
    </Dialog>
</template>
<script lang="ts">
import Dialog from "../lib/Dialog.vue"
import Button from "../lib/Button.vue"
import { ref } from 'vue'
export default {
    components: { Dialog, Button },
    setup() {
        const x = ref(false)
        const toggle = () => {
            x.value = !x.value
        }
        const f1 = () => {
            console.log('1')
            return false
        }
        const f2 = () => {
            console.log('2')
        }
        return { x, toggle, f1, f2 }
    }
}
</script>
