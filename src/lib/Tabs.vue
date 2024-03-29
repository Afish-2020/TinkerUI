<template>
    <div class="gulu-tabs">
        <div class="gulu-tabs-nav" ref="container">
            <div
                class="gulu-tabs-nav-item"
                :class="{ selected: t === selected }"
                :ref="el => { if (t === selected) selectedItem = el }"
                @click="select(t)"
                v-for="(t,index) in titles"
                :key="index"
            >{{ t }}</div>
            <div class="gulu-tabs-nav-indicator" ref="indicator"></div>
        </div>
        <div class="gulu-tabs-content">
            <p class="gulu-tabs-p">已选择：</p>
            <component :is="current" :key="current.props.title" />
        </div>
    </div>
</template>
<script lang="ts">
import { computed, onMounted, onUpdated, ref, watchEffect } from 'vue'
import Tab from "./Tab.vue"
export default {
    props: {
        selected: {
            type: String
        }
    },
    setup(props, context) {
        const selectedItem = ref<HTMLDivElement>(null)
        const indicator = ref<HTMLDivElement>(null)
        const container = ref<HTMLDivElement>(null)
        onMounted(() => {
            watchEffect(() => {
                if (selectedItem.value && indicator.value) {
                    const { width } = selectedItem.value&&selectedItem.value.getBoundingClientRect()
                    indicator.value.style.width = width + 'px'
                    const { left: left1 } = container.value.getBoundingClientRect()
                    const { left: left2 } = selectedItem.value.getBoundingClientRect()
                    const left = left2 - left1
                    indicator.value.style.left = left + 'px'
                }
            }, { flush: 'post' })
        })
        const defaults = context.slots.default()
        defaults.forEach((tag) => {
            if (tag.type !== Tab) {
                throw new Error('Tabs 子标签必须是Tab')
            }
        })
        const current = computed(() => {
            return defaults.filter(t => t.props.title === props.selected)[0]
        })
        const titles = defaults.map(t => {
            return t.props.title
        })
        const select = (t) => {
            context.emit('update:selected', t)
        }
        return { defaults, titles, select, selectedItem, indicator, container, current }
    }
}
</script>
<style lang="scss">
$blue: #40a9ff;
$color: #333;
$border-color: #d9d9d9;
.gulu-tabs {
    &-nav {
        display: flex;
        color: $color;
        border-bottom: 1px solid $border-color;
        position: relative;
        &-item {
            padding: 8px 0;
            margin: 0 16px;
            cursor: pointer;
            &:first-child {
                margin-left: 0;
            }
            &.selected {
                color: $blue;
            }
        }
        &-indicator {
            position: absolute;
            height: 3px;
            background: $blue;
            left: 0;
            bottom: -1px;
            width: 100px;
            transition: all 250ms;
        }
    }
    &-content {
        padding: 8px 0;
    }
    &-p {
        float: left;
        font-size: 14px;
    }
}
</style>