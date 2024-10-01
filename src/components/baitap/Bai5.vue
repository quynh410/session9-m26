<template>
  <div>
    <h1>Bai 5</h1>
    <h3>Gioi tinh : {{ gender }}</h3>
    <input v-model="gender" type="radio" value="nam" />
    <label for="">Nam</label> <br />
    <input v-model="gender" type="radio" value="nu" />
    <label for="">Nu</label> <br />
    <input v-model="gender" type="radio" value="khac" />
    <label for="">Khac</label>
  </div>
</template>

<script setup>
import { ref } from "vue";

const gender = ref("");
</script>

<style></style>
