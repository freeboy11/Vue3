<template>
  <div>{{ student.name }}身价有{{ student.info.social }}亿</div>
  <button @click="changName">改名字</button>
  <button @click="changSocial">改钱数</button>
</template>
<script setup>
import { ref, watch } from "vue";
const student = ref({
  name: "廖某",
  info: {
    social: 1000000000,
    age: 18,
  },
});
const changName = () => {
  student.value.name = "廖总";
};
const changSocial = () => {
  student.value.info.social++;
};
// 监听一个简单的响应式数据
watch(
  () => student.value.name,
  () => {
    console.log("名字发生了改变");
  }
);
// 监听复杂的响应式数据
watch(
  () => student.value.info,
  () => {
    console.log("钱发送了变化");
  },
  {
    deep: true,
    // 一开始就触发
    immediate: true,
  }
);
</script>
<style lang="scss" scoped></style>
