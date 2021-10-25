<template>
    <div>Dialog 示例</div>
    <h2>示例 1</h2>
    <Button @click="toggle">toggle</Button>
    <Dialog v-model:visible="x" :closeOnClickOverlay="false" :ok="f1" :cancel="f2">
        <template v-slot:content>
            <strong>你好</strong>
            <div>hi</div>
        </template>
        <template v-slot:title>
            <strong>加粗的标题</strong>
        </template>
    </Dialog>
    <h2>示例 2</h2>
    <Button @click="showDialog">showDialog</Button>
</template>
<script>
import { openDialog } from "../lib/openDialog.ts"
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
        const showDialog = () => {
            openDialog({
                title: "标题",
                content: "你好",
                OnClickOverlay: false,
                ok() {
                    console.log('ok')
                },
                cancel() {
                    console.log('cancel')
                },
            })
        }
        return { x, toggle, f1, f2, showDialog }
    }
}
</script>