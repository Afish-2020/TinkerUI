<template>
    <button class="gulu-switch" @click="toggle" :class="{ 'gulu-checked': value }">
        <span v-if="value && activeText" class="yes">{{ activeText }}</span>
        <span class="circle"></span>
        <span v-if="!value && inactiveText" class="no">{{ inactiveText }}</span>
    </button>
</template>
<script lang="ts">
export default {
    props: {
        value: Boolean,
        activeText: String,
        inactiveText: String,
    },
    setup(props, context) {
        const toggle = () => {
            context.emit('update:value', !props.value)
            console.log(props.value)
        }
        return { toggle }
    }
}
</script>
<style lang="scss">
$h: 22px;
$h2: $h - 4px;
.gulu-switch {
    height: $h;
    width: $h * 2;
    border: none;
    background: #bfbfbf;
    border-radius: $h / 2;
    position: relative;
    > .circle {
        position: absolute;
        top: 2px;
        left: 2px;
        height: $h2;
        width: $h2;
        background: white;
        border-radius: $h2 / 2;
        transition: all 250ms;
    }
    > .no {
        position: absolute;
        top: 1px;
        left: 25px;
        color: white;
        font-size: 14px;
    }

    &.gulu-checked {
        background: #1890ff;
        > span {
            left: calc(100% - #{$h2} - 2px);
        }
        > .yes {
            position: absolute;
            top: 1px;
            left: 5px;
            color: white;
            font-size: 14px;
        }
    }
    &:focus {
        outline: none;
    }
    &:active {
        > span {
            width: $h2 + 4px;
        }
    }
    &.gulu-checked:active {
        > span {
            width: $h2 + 4px;
            margin-left: -4px;
        }
    }
}
</style>