<template>
    <div class="topnav">
           <div class="logo" @click="ToggleAside">LOGO</div>
           <ul class="menu">
               <li>菜单1</li>
               <li>菜单2</li>
               </ul>           
       </div>
</template>
<script lang="ts">
import { inject, Ref } from 'vue'
export default{
    setup() {
        const asideVisible = inject<Ref<boolean>>('asideVisible')
        const ToggleAside = () =>{
            asideVisible.value = !asideVisible.value 
        }
        console.log('Topnav的asideVisible'+asideVisible.value) 
        return{ToggleAside}
    }
}
</script>
<style lang="scss" scoped>
.topnar{border: 1px solid red;}
  
.topnav {
  background: pink;
  display: flex;
  padding: 16px;
  position: relative;
  z-index: 10;
  > .logo {
    max-width: 6em;
    margin-right: auto;
  }
  > .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;
    > li {
      margin: 0 1em;
    }
  }
}
</style>