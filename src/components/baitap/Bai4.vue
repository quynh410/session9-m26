<template>
  <div>
    <h1>Bai 4</h1>
    <h3>Tien do hoanh thanh: {{ range }} %</h3>
    <input type="range" v-model="range">
  </div>
</template>

<script setup>
import { ref } from "vue";
    const range = ref('');
</script>

<style></style>
