<template>
  <div>
    <h1>Bai 9</h1>
    <h3>Dang ki tai khoan</h3>
    <form @submit.prevent="handleSubmit">
      <label for="name">Tên sinh viên:</label><br />
      <input type="text" id="name" v-model="student.name" ref="nameInput" />
      <br />
      <span v-if="errors.name">{{ errors.name }}</span><br />

      <label for="email">Email:</label><br />
      <input type="email" id="email" v-model="student.email" />
      <br />
      <span v-if="errors.email">{{ errors.email }}</span><br />

      <label for="password">Mật khẩu:</label><br />
      <input type="password" id="password" v-model="student.password" />
      <br />
      <span v-if="errors.password">{{ errors.password }}</span><br />

      <label for="phone">Số Điện Thoại:</label><br />
      <input type="text" id="phone" v-model="student.phone" /><br />
      <span v-if="errors.phone">{{ errors.phone }}</span>

      <br /><br />

      <button type="submit">Đăng ký</button>
    </form>

    <div v-if="successMessage">{{ successMessage }}</div>
  </div>
</template>

<script setup>
import { ref, reactive } from "vue";
const student = reactive({
  name: "",
  email: "",
  password: "",
  phone: "",
});
const errors = reactive({
  name: "",
  email: "",
  password: "",
  phone: "",
});

const successMessage = ref("");
const emailList = ref(JSON.parse(localStorage.getItem("emailList")) || []);

const validateForm = () => {
  let valid = true;

  if (!student.name) {
    errors.name = "Tên sinh viên không được để trống";
    valid = false;
  } else {
    errors.name = "";
  }

  if (!student.email) {
    errors.email = "Email không được để trống";
    valid = false;
  } else if (emailList.value.includes(student.email)) {
    errors.email = "Email đã được đăng ký";
    valid = false;
  } else {
    errors.email = "";
  }

  if (!student.password) {
    errors.password = "Mật khẩu không được để trống";
    valid = false;
  } else {
    errors.password = "";
  }

  if (!student.phone) {
    errors.phone = "Số điện thoại không được để trống";
    valid = false;
  } else {
    errors.phone = "";
  }

  return valid;
};

const handleSubmit = () => {
  if (validateForm()) {
    localStorage.setItem("student", JSON.stringify(student));

    emailList.value.push(student.email);
    localStorage.setItem("emailList", JSON.stringify(emailList.value));

    student.name = "";
    student.email = "";
    student.password = "";
    student.phone = "";
    alert("Đăng ký tài khoản thành công");

    setTimeout(() => {
      nameInput.value.focus();
    }, 0);
  }
};

const nameInput = ref(null);
</script>

<style>
span {
  color: red;
}
</style>
