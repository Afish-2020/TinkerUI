<template>
    <div class="demo">
        <!-- <h2>{{ component.__sourceCodeTitle }}</h2> -->
        <div class="demo-component">
            <component :is="component" />
        </div>
        <div class="demo-actions">
            <Button v-if="codeVisible" @click="hideCode">隐藏代码</Button>
            <Button v-else @click="showCode">查看代码</Button>
        </div>
        <div class="demo-code" v-if="codeVisible">
            <pre class="language-css" v-html="html"></pre>
        </div>
    </div>
</template>
<script lang="ts">
import { computed, ref } from 'vue'
import Button from '../lib/Button.vue'
import "prismjs"
const Prism = (window as any).Prism
export default {
    components: { Button },
    props: {
        component: {
            type: Object
        }
    },
    setup(props) {
        const html = computed(() => {
            return Prism.highlight(props.component.__sourceCode, Prism.languages.html, 'html')
        })
        const codeVisible = ref(false)
        const showCode = () => {
            codeVisible.value = true
        }
        const hideCode = () => {
            codeVisible.value = false
        }
        return { Prism, html, codeVisible, showCode, hideCode }
    }
}
</script>
<style lang="scss" scoped>
$border-color: #d9d9d9;
.demo {
    // border: 1px solid $border-color;
    margin: 16px 0 32px;
    > h2 {
        font-size: 18px;
        padding: 8px 0;
    }
    &-component {
        border: 1px solid $border-color;
        padding: 16px 16px;
    }
    &-actions {
        padding: 8px 16px;
        border-left: 1px dashed $border-color;
        border-right: 1px dashed $border-color;
        border-bottom: 1px dashed $border-color;
    }
    &-code {
        padding: 8px 16px;
        border-left: 1px dashed $border-color;
        border-right: 1px dashed $border-color;
        border-bottom: 1px dashed $border-color;
        > pre {
            line-height: 1.1;
            font-family: Consolas, "Courier New", Courier, monospace;
            margin: 0;
        }
    }
}
</style>
<style lang="scss">
@import "prismjs/themes/prism-okaidia.css";
</style>