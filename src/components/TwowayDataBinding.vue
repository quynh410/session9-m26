<template>
  <div>
    <h1>Twoway Data Binding</h1>
    <form @submit="handleSubmit"> 
      <h2>User Name : {{userInfo.userName }}</h2>
      <h2>Ngay Sinh : {{userInfo.dateOfBirth }}</h2>
      <h3>Gioi Tinh : {{userInfo.gender }}</h3>
      <h3>So Thich :  {{userInfo.hobbies }}</h3>
      <h3>Them Moi Nguoi Dung</h3>
      <label for="username">Username : </label>
      <input v-model="userName" type="text" /> <br />
      <label for="data">Ngay Sinh: </label>
      <input v-model="dateOfBirth" type="date" /><br />
      <label for="gender">Gioi Tinh :</label>
      <div>
        Nam <input name="gender" v-model="userInfo.gender" type="radio" value="Nam" /> 
        Nu  <input name="gender" v-model="userInfo.gender" type="radio" value="Nu" /> 
        Khac<input name="gender" v-model="userInfo.gender" type="radio" value="Khac" />
      </div>
      <div>So thich</div>
      <div>
        <input type="checkbox" v-model="userInfo.hobbies" value="game" /> Choi game 
        <input type="checkbox" v-model="userInfo.hobbies" value="code" /> Code
        <input type="checkbox" v-model="userInfo.hobbies" value="swim" /> Boi loi 
        <input type="checkbox" v-model="userInfo.hobbies" value="volleyball" /> Bong chuyen
        <input type="checkbox" v-model="userInfo.hobbies" value="outffit" /> Thoi Trang
      </div>
      <button>Them</button>
    </form>
  </div>
</template>

<script setup>
import { reactive, ref } from "vue";
const userInfo = reactive({
    userName: "",
    dateOfBirth: "",
    gender: "0",
    hobbies: [],
})
const handleSubmit = (e)=>{
    // ngan chan su kien load lai trang
    // e.preventDefault();
    
    // Reset form
    userName.value = "";
    dateOfBirth.value = "";
    gender.value = "";
    hobbies.value = [];
  
}
</script>

<style></style>
