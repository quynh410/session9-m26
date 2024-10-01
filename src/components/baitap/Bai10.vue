<template>
  <div>
    <h1>Bai 10</h1>
    <h3>Đăng nhập tài khoản</h3>
    <form @submit.prevent="handleSubmit">
      <label for="email">Email:</label><br />
      <input type="email" id="email" v-model="loginData.email" />
      <br />
      <span v-if="errors.email">{{ errors.email }}</span><br />

      <label for="password">Mật khẩu:</label><br />
      <input type="password" id="password" v-model="loginData.password" />
      <br />
      <span v-if="errors.password">{{ errors.password }}</span><br /><br />

      <button type="submit">Đăng nhập</button>
    </form>

    <div v-if="loginMessage">{{ loginMessage }}</div>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue';
const loginData = reactive({
  email: '',
  password: ''
});
const errors = reactive({
  email: '',
  password: ''
});
const loginMessage = ref('');

const validateForm = () => {
  let valid = true;

  if (!loginData.email) {
    errors.email = 'Email không được để trống';
    valid = false;
  } else {
    errors.email = '';
  }

  if (!loginData.password) {
    errors.password = 'Mật khẩu không được để trống';
    valid = false;
  } else {
    errors.password = '';
  }

  return valid;
};

const handleSubmit = () => {
  if (validateForm()) {
    const storedData = JSON.parse(localStorage.getItem('student'));

    if (storedData && storedData.email === loginData.email && storedData.password === loginData.password) {
        alert("Đăng nhập thanh công")
    } else {
        alert("Đăng nhập thất bại")
    }
  }
};
</script>

<style>
span {
  color: red;
}
</style>
