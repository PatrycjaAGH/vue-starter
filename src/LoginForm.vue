<template>
  <div>

    <input type=" email" v-model="email">
    <button @click="logMeIn()">Zaloguj się</button>
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      email: ''
    }
  },
  methods: {
    logMeIn() {
      this.$emit('login', this.email);
    }
  }
}
</script>