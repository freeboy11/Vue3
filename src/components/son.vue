<template>
  <div>小廖{{ num }}万</div>
</template>

<script setup>
import { inject } from "vue";

const num = inject("mynum");
</script>

<style lang="scss" scoped></style>
