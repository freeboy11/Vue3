<template>
  <div>
    <h1>廖总身价{{ num }}亿</h1>
  </div>
  <fa></fa>
  <son></son>
</template>

<script setup>
import son from "./components/son.vue";
import fa from "./components/fa.vue";
import { provide, ref } from "vue";
const num = ref(100);
provide("mynum", num);
</script>

<style>
div {
  background-color: pink;
}
</style>
