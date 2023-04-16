<template>
  <div class="my-app">
    <h1>Witaj w systemie zapisów na zajęcia!</h1>
    <div v-if="loggedIn">
      Zalogowany {{ email }} !!!!!!!
      <a @click="logMeOut()">Wyloguj</a>

    </div>
    <div v-else>
      <input type=" email" v-model="email">
      <button @click="alertMyEmail()">Zaloguj się</button>
      <div v-if="email.length < 10">Ale masz krótki adres!</div>
      <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
      <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
    </div>
    </div>
</template>

<script>

export default {
  methods: {
    logMeIn() {
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
