<template>
  <div>
    <h1>Bai 3</h1>
    <h3>Ngay sinh : {{ date }}</h3>
    <input type="date" v-model="date" />
  </div>
</template>

<script setup>
import { ref } from "vue";

const date = ref("");
</script>

<style></style>
