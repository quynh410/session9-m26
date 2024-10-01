<template>
  <div>
    <h1>Bai 7</h1>
    <h3>Them moi san pham</h3>

    <label for="">Ma San Pham</label><br />
    <input type="text" v-model="product.maSanPham" /> <br />

    <label for="">Ten San Pham</label><br />
    <input type="text" v-model="product.tenSanPham" /> <br />

    <label for="">Gia San Pham</label><br />
    <input type="text" v-model="product.giaSanPham" /> <br />

    <label for="">So Luong</label><br />
    <input type="number" v-model="product.soLuong" /> <br />

    <button @click="handleAddProduct">Them moi</button>


  </div>
</template>

<script setup>
import { reactive } from "vue";

const product = reactive({
  maSanPham: "",
  tenSanPham: "",
  giaSanPham: "",
  soLuong: 0,
});

const handleAddProduct = () => {
  console.log("Product added:", product);
};
</script>

<style></style>
