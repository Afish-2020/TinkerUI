<demo>
一键打开 Dialog
</demo>

<template>
    <Button @click="showDialog" theme="link">打开Dialog</Button>
</template>
<script>
import { openDialog } from "../lib/openDialog.ts"
import Dialog from "../lib/Dialog.vue"
import Button from "../lib/Button.vue"
export default {
    components: { Dialog, Button },
    setup() {
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
        return { showDialog }
    }
}
</script>
