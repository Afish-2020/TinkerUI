<template>
    <div class="topnav">
        <router-link to="/" class="logo">
            <svg class="icon">
                <use xlink:href="#icon-bell1" />
            </svg>
        </router-link>
        <ul class="menu">
            <li>
                <router-link to="/doc">文档</router-link>
            </li>
        </ul>
        <span v-if="toggleMenuButtonVisible" class="toggleAside" @click="ToggleAside">
            <svg class="icon">
                <use xlink:href="#icon-menu" />
            </svg>
        </span>
    </div>
</template>
<script lang="ts">
import { inject, Ref } from 'vue'
export default {
    props: {
        toggleMenuButtonVisible: {
            type: Boolean,
            default: false
        }
    },
    setup() {
        const asideVisible = inject<Ref<boolean>>('asideVisible')
        const ToggleAside = () => {
            asideVisible.value = !asideVisible.value
        }
        return { ToggleAside }
    }
}
</script>
<style lang="scss" scoped>
$color: #393f93;
.topnav {
    color: $color;
    display: flex;
    padding: 16px;
    position: relative;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 10;
    justify-content: center;
    align-items: center;
    z-index: 11;
    background: white;
    box-shadow: 4px 3px 5px rgba(0, 0, 0, 0.05);
    > .logo {
        max-width: 6em;
        margin-right: auto;
        > svg {
            width: 32px;
            height: 32px;
        }
    }
    > .menu {
        display: flex;
        white-space: nowrap;
        flex-wrap: nowrap;
        > li {
            margin: 0 1em;
        }
    }
    > .toggleAside {
        width: 32px;
        height: 32px;
        position: absolute;
        left: 16px;
        top: 50%;
        transform: translateY(-50%);
        display: none;
        // background: fade-out(black, 0.9);
        > svg {
            position: absolute;
            top: 50%;
            transform: translate(-3%, -50%);
            width: 2em;
            height: 2em;
        }
    }
    @media (max-width: 500px) {
        > .menu {
            display: none;
        }
        > .logo {
            margin: 0 auto;
        }
        > .toggleAside {
            display: block;
        }
    }
}
</style>