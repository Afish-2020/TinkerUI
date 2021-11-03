<demo>
支持 level
</demo>

<template>
    <div class="button-style">
        <Button>默认按钮</Button>
        <Button level="main">主要按钮</Button>
        <Button level="success">成功按钮</Button>
        <Button level="warning">警告按钮</Button>
        <Button level="danger">危险按钮</Button>
    </div>
    <div>
        <Button level="main" theme="link">主要链接按钮</Button>
        <Button theme="link">默认链接按钮</Button>
        <Button level="danger" theme="link">危险链接按钮</Button>
        <Button level="success" theme="link">成功链接按钮</Button>
        <Button level="warning" theme="link">警告链接按钮</Button>
    </div>
    <div>
        <Button level="main" theme="text">主要文字按钮</Button>
        <Button theme="text">默认文字按钮</Button>
        <Button level="danger" theme="text">危险文字按钮</Button>
        <Button level="warning" theme="text">警告文字按钮</Button>
        <Button level="success" theme="text">成功文字按钮</Button>
    </div>
</template>
<script lang="ts">
import Button from "../lib/Button.vue"
export default {
    components: {
        Button
    }
}
</script>
<style>
.button-style {
    margin: 10px;
}
</style>
