<template>
  <div>
    <h1>Bai 8 </h1>
    <h3>Them moi tai khoan</h3>
    <label for="">Ho va ten </label><br>
    <input type="text" id="hoTen" v-model="newAccount.hoTen" /> <br>
    <label for="">Email </label><br>
    <input type="email" id="email" v-model="newAccount.email" /> <br>
    <label for="">Mat khau </label><br>
    <input type="password" id="matKhau" v-model="newAccount.matKhau" /><br>
    <label for="">Xac nhan mat khau </label><br>
    <input type="password" id="xacNhanMatKhau" v-model="newAccount.xacNhanMatKhau" /> <br>
    <button @click="handleAddAccount">Them tai khoan</button>
  </div>
</template>

<script setup>
  import { reactive, ref } from 'vue'
  const newAccount = reactive({
    hoTen: '',
    email: '',
    matKhau: '',
    xacNhanMatKhau: ''
  })
  const handleAddAccount = ()=>{
    console.log("Add Account" , newAccount);
    
  }
</script>

<style>

</style>