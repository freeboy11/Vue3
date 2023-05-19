<template>
  <div>我是子组件</div>
  <form>账号 <input type="text" /> 密码 <input type="text" /></form>
  <div>{{ msg }}</div>
</template>
<script setup>
import { ref } from "vue";
const msg = ref("你好世界");
// 固定写法  暴露
defineExpose({ msg });
</script>

<style scoped>
div {
  background-color: pink;
}
</style>
