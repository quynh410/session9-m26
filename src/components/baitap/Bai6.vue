<template>
  <div>
    <h1>Bai 6</h1>
    <h3>So thich : {{hobby}}</h3>
    <input v-model="hobby"  type="checkbox" value="Da bong">
    <label for=""> Da bong</label>
    <input v-model="hobby"  type="checkbox" value="Bong chuyen">
    <label for="">Bong Chuyen</label>
    <input v-model="hobby"  type="checkbox" value="Code">
    <label for="">Code</label>
    <input v-model="hobby"  type="checkbox" value="Boi loi">
    <label for="">Boi loi</label>
  </div>
</template>

<script setup>
import { ref } from "vue";

    const hobby = ref([]);
</script>

<style>

</style>