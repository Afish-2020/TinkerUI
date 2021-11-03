<demo>
常规用法
</demo>

<template>
    <Button @click="toggle" theme="link">打开处理Button的Dialog</Button>
    <Dialog v-model:visible="x" :closeOnClickOverlay="false" :ok="f1" :cancel="f2">
        <template v-slot:content>
            <strong>你好</strong>
            <div>hi</div>
        </template>
        <template v-slot:title>
            <strong>加粗的标题</strong>
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
            // return false
        }
        const f2 = () => {
            console.log('2')
        }
        return { x, toggle, f1, f2 }
    }
}
</script>
