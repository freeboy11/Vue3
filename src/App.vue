<template>
  <div>{{ student.name }}身价有{{ student.info.social }}亿</div>
  <button @click="changName">改名字</button>
  <button @click="changSocial">改钱数</button>
</template>
<script setup>
import { onMounted, ref, watch } from "vue";
console.log("你好");
// 一般写接口等经常用的生命周期  可以多次调用   方便配合async 使用  现在是假的数据
onMounted(async () => {
  console.log("我是在渲染之后出现的");
  const res = await List();
});
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
