<template>
    <div>
        <input :type="type" v-model="value" :disabled="disabled" :placeholder="placeholder" />
        <div v-if="!disabled && type === 'text' && pattern" class="text">
            <span>支持双向绑定</span>
            <span class="textValue">{{ value }}</span>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        disabled: {
            type: Boolean,
            default: false
        },
        value: String,
        type: {
            type: String,
            default: 'text'
        },
        placeholder: String,
        pattern: {
            type: Boolean,
            default: false
        }
    },
    setup(props) {
    }
}
</script>
<style lang="scss">
$h: 32px;
$border-color: #d9d9d9;
$color: #333;
$blue: #40a9ff;
$radius: 4px;
$red: #f56c6c;
$grey: grey;
input {
    box-sizing: border-box;
    height: $h;
    padding: 0 12px;
    background: white;
    border: 1px solid #d9d9d9;
    border-radius: $radius;
    box-shadow: 0 1px 0 fade-out(black, 0.95);
    &:focus {
        outline: none;
        border: 1px solid #20a0ff;
    }
    &[disabled] {
        background: #f5f7fa;
    }
}
.text {
    margin-top: 10px;
    > span {
        font-size: 14px;
        padding: 8px 0;
    }
    .textValue {
        display: flex;
        align-items: center;
        box-sizing: border-box;
        height: $h;
        width: 6 * $h;
        padding: 0 12px;
        background: white;
        border: 1px solid #d9d9d9;
        border-radius: $radius;
        box-shadow: 0 1px 0 fade-out(black, 0.95);
    }
}
</style>