<template>
    <template v-if="visible">
        <teleport to="body">
            <div class="gulu-dialog-overlay" @click="OnClickOverlay"></div>
            <div class="gulu-dialog-wrapper">
                <div class="gulu-dialog">
                    <header>
                        <slot name="title" />
                        <span @click="close" class="gulu-dialog-close"></span>
                    </header>
                    <main>
                        <slot name="content" />
                    </main>
                    <footer v-if="ok">
                        <Button @click="ok1">确定</Button>
                        <Button @click="cancel1">取消</Button>
                    </footer>
                </div>
            </div>
        </teleport>
    </template>
</template>
<script>
import Button from "./Button.vue"
export default {
    components: { Button },
    props: {
        title: {
            type: String,
            default: "提示"
        },
        visible: {
            type: Boolean,
            default: false
        },
        closeOnClickOverlay: {
            type: Boolean,
            default: true
        },
        ok: {
            type: Function,
        },
        cancel: {
            type: Function
        }
    },
    setup(props, context) {
        const close = () => {
            context.emit("update:visible", false)
        }
        const OnClickOverlay = () => {
            if (props.closeOnClickOverlay) {
                close()
            }
        }
        const ok1 = () => {
            if (props.ok?.() !== false) {
                close()
            }
        }
        const cancel1 = () => {
            if (props.cancel?.() !== false) {
                close()
            }
        }
        return { close, OnClickOverlay, ok1, cancel1 }
    }
}
</script>
<style lang="scss">
$radius: 4px;
$border-color: #d9d9d9;
.gulu-dialog {
    background: white;
    border-radius: $radius;
    box-shadow: 0 0 3px fade_out(black, 0.5);
    min-width: 15em;
    min-height: 10em;
    max-width: 90%;
    &-overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: fade_out(black, 0.5);
        z-index: 11;
    }
    &-wrapper {
        position: fixed;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        z-index: 11;
    }
    > header {
        padding: 12px 16px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        font-size: 20px;
    }
    > main {
        padding: 12px 16px;
    }
    > footer {
        padding: 12px 16px;
        text-align: right;
    }
    &-close {
        position: relative;
        display: inline-block;
        width: 16px;
        height: 16px;
        cursor: pointer;
        &::before,
        &::after {
            content: "";
            position: absolute;
            height: 1px;
            background: black;
            width: 100%;
            top: 20%;
            left: 50%;
        }
        &::before {
            transform: translate(-50%, -50%) rotate(-45deg);
        }
        &::after {
            transform: translate(-50%, -50%) rotate(45deg);
        }
    }
}
</style>