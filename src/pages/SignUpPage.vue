<template>
  <h1>Sign Up</h1>
  <label for="username">Username</label>
  <input id="username" />

  <label for="e-mail">E-mail</label>
  <input id="e-mail" />

  <label for="password">Password</label>
  <input id="password" type="password" @input="(event) => password = event.target.value"/>

  <label for="password-repeat">Password Repeat</label>
  <input id="password-repeat" type="password" v-on:input="(event) => passwordRepeat = event.target.value"/>

  <button :disabled="isDisabled">Sign Up</button>
</template>

<script>
export default {
  name: "SignUpPage",
  data() {
    return {
      disabled: true,
      username: '',
      password: '',
      passwordRepeat: ''
    };
  },
  computed: {
    isDisabled(){
      console.log("isDisabledComputed method is running");
      return this.password && this.passwordRepeat ? this.password !== this.passwordRepeat : true;
    },
  }
}
</script>