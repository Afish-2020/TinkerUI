<template>
    <div class="layout">
        <Topnav toggleMenuButtonVisible class="nav" />
        <div class="content">
            <aside v-if="asideVisible">
                <h2>文档</h2>
                <ol>
                    <li>
                        <router-link to="/doc/intro">介绍</router-link>
                    </li>
                    <li>
                        <router-link to="/doc/install">安装</router-link>
                    </li>
                    <li>
                        <router-link to="/doc/get-started">开始使用</router-link>
                    </li>
                </ol>
                <h2>组件列表</h2>
                <ol>
                    <li>
                        <router-link to="/doc/switch">Switch 组件</router-link>
                    </li>
                    <li>
                        <router-link to="/doc/button">Button 组件</router-link>
                    </li>
                    <li>
                        <router-link to="/doc/dialog">Dialog 组件</router-link>
                    </li>
                    <li>
                        <router-link to="/doc/input">Input 组件</router-link>
                    </li>
                    <li>
                        <router-link to="/doc/tabs">Tabs 组件</router-link>
                    </li>
                </ol>
            </aside>
            <main>
                <router-view />
            </main>
        </div>
    </div>
</template>
<script lang="ts">
import { inject, Ref } from 'vue'
import Topnav from '../components/Topnav.vue'
export default {
    components: { Topnav },
    setup() {
        const asideVisible = inject<Ref<boolean>>('asideVisible')
        return { asideVisible }
    }
}
</script>
<style lang="scss" scoped>
$aside-index: 10;
.layout {
    display: flex;
    flex-direction: column;
    height: 100vh;
    > .nav {
        flex-shrink: 0;
    }
    > .content {
        flex-grow: 1;
        padding-top: 60px;
        padding-left: 156px;
        @media (max-width: 500px) {
            padding-left: 0;
        }
    }
}
.content {
    display: flex;
    > aside {
        flex-shrink: 0;
    }
    > main {
        flex-grow: 1;
        // padding: 60px;
        padding: 40px 60px 0 180px;
        background: white;
        @media (max-width: 500px) {
            padding: 60px;
        }
    }
}
aside {
    background: white;
    width: 280px;
    padding: 16px 0;
    position: fixed;
    top: 0;
    left: 0;
    padding-top: 70px;
    height: 100%;
    z-index: $aside-index;
    // box-shadow: 4px 3px 4px rgba(0, 0, 0, 0.1);
    border: 1px solid #f0f0f0;
    > h2 {
        margin: 16px 0;
        padding: 0 50px;
    }
    > ol {
        > li {
            font-size: 16px;

            > a {
                display: block;
                padding: 8px 64px;
                &:hover {
                    text-decoration: none;
                }
            }
            .router-link-active {
                background: linear-gradient(
                    90deg,
                    rgba(230, 247, 255, 1) 0%,
                    rgba(163, 218, 255, 1) 99%,
                    rgba(32, 160, 255, 1) 99%,
                    rgba(32, 160, 255, 1) 100%
                );
                text-decoration: none;
            }
        }
    }
}
main {
    overflow: auto;
}
</style> 