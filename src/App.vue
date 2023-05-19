<template>
  <div>廖总有{{ msg }}老婆</div>
  <button @click="add">+</button>
</template>

<script setup>
import { ref, watch } from "vue";
const msg = ref(10);
const add = () => {
  msg.value++;
};
// 监听一个响应式数据
watch(msg, () => {
  console.log("改变", msg.value);
});
</script>
<style lang="scss" scoped></style>
