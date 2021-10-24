<template>
    <div>Button 示例</div>
    <Button>你好</Button>
    <Button theme="button">你好</Button>
    <Button theme="link">你好</Button>
    <Button theme="text">你好</Button>
    <div>示例 2</div>
    <div>
        <Button size="big">大大大</Button>
        <Button>普普通通</Button>
        <Button size="small">小小小</Button>
    </div>
    <div>
        <Button size="big" theme="link">大大大</Button>
        <Button theme="link">普普通通</Button>
        <Button size="small" theme="link">小小小</Button>
    </div>
    <div>
        <Button size="big" theme="text">大大大</Button>
        <Button theme="text">普普通通</Button>
        <Button size="small" theme="text">小小小</Button>
    </div>
    <div>示例 3</div>
    <div>
        <Button level="main">主要按钮</Button>
        <Button>普通按钮</Button>
        <Button level="danger">危险按钮</Button>
    </div>
    <div>
        <Button level="main" theme="link">主要链接按钮</Button>
        <Button theme="link">普通链接按钮</Button>
        <Button level="danger" theme="link">危险链接按钮</Button>
    </div>
    <div>
        <Button level="main" theme="text">主要文字按钮</Button>
        <Button theme="text">普通文字按钮</Button>
        <Button level="danger" theme="text">危险文字按钮</Button>
    </div>
    <div>示例 4</div>
    <div>
        <Button disabled>禁用按钮</Button>
        <Button disabled theme="link">禁用链接按钮</Button>
        <Button disabled theme="text">禁用文字按钮</Button>
    </div>
    <div>示例 5</div>
    <div>
        <Button loading>加载中</Button>
        <Button>加载完成</Button>
    </div>
</template>
<script lang="ts">
import Button from "../lib/Button.vue"
export default {
    components: { Button },
    setup() {
        const onClick = () => {
            console.log('hi')
        }
        return { onClick }
    }
}
</script>