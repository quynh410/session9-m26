<template>
  <div>
    <h1>Bai 1</h1>
    <label for="">Email : </label>
    <input type="text" v-model="email" />
    <p>Gia tri : {{ email }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";

const email = ref("");
</script>

<style></style>
