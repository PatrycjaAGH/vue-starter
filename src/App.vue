<template>
  <div class="my-app">
    <h1>Witaj w systemie zapisów na zajęcia!</h1>
    <div v-if="loggedIn">
      Zalogowany {{ email }} !!!!!!!
      <a @click="logMeOut()">Wyloguj</a>
    </div>
    <div v-else>
    <LoginForm @login="(username) => logMeIn(username)"></LoginForm>
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  components: {LoginForm},

  methods: {
    logMeIn(username) {
      this.email = username;
      this.loggedIn = true;
    },
    logMeOut() {
      this.loggedIn = false;
    },

    alertMyEmail() {
      alert(this.email);
    }
  },
  data() {
    return {
      email: 'patrycja.barbara.szczepanska@gmail.com',
      loggedIn: false,
      password: ''
    };
  }

}
</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
