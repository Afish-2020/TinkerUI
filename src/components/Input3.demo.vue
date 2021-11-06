<demo>
常规用法
</demo>

<template>
    <div>
        <Input placeholder="文本类型" />
        <div>
            <Input type="password" placeholder="密码类型" />
        </div>
    </div>
</template>
<script>
import Input from "../lib/Input.vue"
export default {
    setup() {
        return { Input }
    }

}
</script>
<style scoped>
input {
    margin-bottom: 10px;
}
</style>