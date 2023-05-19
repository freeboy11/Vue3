<template>
  <button @click="toggle">显示隐藏图片</button>
  <img v-show="show" alt="Vue logo" src="./assets/preview.gif" />
  <hr />
  计数器：{{ count }} <button @click="increment">累加</button>
  <p>{{ state.name }}</p>
  <p>{{ state.age }}</p>
  <div>{{ msg }}</div>
  <button @click="translate">翻译</button>
</template>
<script>
// ref 就是一个组合式API
import { reactive, ref } from "vue";
export default {
  setup() {
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

    return { show, toggle, count, increment, state, translate, msg };
  },
};
</script>
