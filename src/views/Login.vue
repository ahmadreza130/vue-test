<template>
  <h3>login</h3>
  <input v-model="username" type="text" placeholder="username" />
  <input v-model="password" type="password" placeholder="password" />
  <button @click="login">login</button>
  <button @click="logout">logout</button>
</template>

<script>
import axios from "axios";
export default {
  name: "Home",
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    async login() {
      const { data } = await axios.post("http://localhost:8000/resume/login/", {
        username: this.username,
        password: this.password,
      });
      localStorage.setItem("token", data);
      this.username = "";
      this.password = "";
    },
     logout() {
      localStorage.removeItem('token')
    },
  },
};
</script>
