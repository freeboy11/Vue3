<template>
  <div>我是子组件</div>
  <form>账号 <input type="text" /> 密码 <input type="text" /></form>
  <div>{{ msg }}</div>
  <h1>父组件里面的内容{{ car }}</h1>
  <button @click="changcolor">点击</button>
</template>
<script setup>
import { ref } from "vue";
const msg = ref("你好世界");
// 固定写法  暴露
defineExpose({ msg });
// 接收父组件里面的内容
defineProps({ car: String });
// 子传父
// 获取emit
const emit = defineEmits(["myColor"]);
const changcolor = () => {
  emit("myColor", "你干嘛");
};
</script>

<style scoped>
div {
  background-color: pink;
}
button {
  background-color: skyblue;
}
</style>
