<template>
  <div>
    <h1>Bai 2</h1>
    <h3>Mau sac</h3>
    <input type="color" v-model="color" />
    <p>Ma mau : {{ color }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";

const color = ref("");
</script>

<style></style>
