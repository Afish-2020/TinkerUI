<template>
  <div class="topnavAndBanner">
    <Topnav />
    <div class="banner">
      <h1>Tinker UI</h1>
      <p class="little-title">基于Vue的UI框架</p>
      <div class="actions">
        <a href="https://github.com/Afish-2020/TinkerUI">GitHUb</a>
        <router-link to="/doc">开始</router-link>
      </div>
    </div>
  </div>
  <div class="features">
    <ul>
      <li>
        <svg>
          <use xlink:href="#icon-vue" />
        </svg>
        <h3>基于 Vue 3</h3>
        <p>骄傲地使用了 Vue 3 Composition API</p>
      </li>
      <li>
        <svg>
          <use xlink:href="#icon-ts" />
        </svg>
        <h3>基于 TypeScript</h3>
        <p>源代码采用 TypeScript 书写</p>
      </li>
      <li>
        <svg>
          <use xlink:href="#icon-light" />
        </svg>
        <h3>代码易读</h3>
        <p>每个组件的源代码都极其简洁</p>
      </li>
    </ul>
  </div>
</template>
<script lang="ts">
import Topnav from "../components/Topnav.vue";
export default {
  components: { Topnav },
}
</script>
<style lang="scss" scoped>
$green: #393f93;
$border-radius: 20px;
$color: #0b0a0f;
.topnavAndBanner {
  // background: linear-gradient(
  //   145deg,
  //   rgba(227, 255, 253, 1) 0%,
  //   rgba(183, 233, 230, 1) 100%
  // );
  clip-path: ellipse(80% 60% at 50% 40%);
  background: #fff4f2;
}
.features {
  margin: 64px auto;
  padding: 0 16px;
  @media (min-width: 800px) {
    width: 800px;
    > ul {
      > li {
        width: 50%;
      }
    }
  }

  @media (min-width: 1200px) {
    width: 1200px;
    > ul {
      > li {
        width: 33.3333%;
      }
    }
  }
  > ul {
    display: flex;
    flex-wrap: wrap;
    > li {
      // width: 400px;
      margin: 16px 0;
      display: grid;
      justify-content: start;
      align-content: space-between;
      grid-template-areas:
        "icon title"
        "icon text";
      grid-template-columns: 80px auto;
      grid-template-rows: 1fr auto;
      > svg {
        grid-area: icon;
        width: 64px;
        height: 64px;
      }
      > h3 {
        grid-area: title;
        font-size: 28px;
      }
      > p {
        grid-area: text;
      }
    }
  }
}
.banner {
  color: $color;
  padding: 100px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  > h1 {
    font-size: 60px;
    font-weight: bolder;
  }
  > .little-title {
    color: #a29f9f;
  }
  > .actions {
    padding: 8px 0;
    a {
      margin: 20px 20px 0;
      background: $green;
      color: white;
      display: inline-block;
      padding: 8px 24px;
      border-radius: $border-radius;
      &:hover {
        text-decoration: none;
      }
    }
  }
}
</style>