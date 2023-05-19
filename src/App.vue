<template>
  <button @click="toggle">显示隐藏图片</button>
  <img v-show="show" alt="Vue logo" src="./assets/preview.gif" />
  <hr />
  计数器：{{ count }} <button @click="increment">累加</button>
  <p>{{ state.name }}</p>
  <p>{{ state.age }}</p>
  <div>{{ msg }}</div>
  <button @click="translate">翻译</button>
  <!-- 使用计算属性 -->
  <div>成绩:{{ score }}</div>
  <div>优秀成绩:{{ excescore }}</div>
</template>
<script setup>
// ref 就是一个组合式API
import { reactive, ref, computed } from "vue";
// 使用计算属性
const score = ref([20, 40, 50, 70, 80, 90, 100]);
const excescore = computed(() => score.value.filter((item) => item >= 80));
// 显示隐藏
const show = ref(true);
const toggle = () => {
  show.value = !show.value;
};
// 计数器
const count = ref(0);
const increment = () => {
  count.value++;
};
// reactive函数
// 2 创建响应式数据对象
const state = reactive({ name: "廖总", age: 18 });
// 注意  使用ref的时候要.value
let msg = ref("我爱你");
const translate = () => {
  msg.value = "LOVE";
};
</script>
