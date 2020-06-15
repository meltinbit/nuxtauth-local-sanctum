<template>
  <div>
    <h1>Login</h1>
    <nuxt-link to="/">home</nuxt-link>
    <input v-model="form.email">
    <input v-model="form.password">
    <button @click="login">LOGIN</button>
  </div>
</template>

<script>


export default {
  data() {
    return {
      form: {
        email: 'fabio@fabiomangolini.net',
        password: 'zxasqw12'
      }
    }
  },
  methods: {
    login() {
      this.$auth.loginWith('local', {
        data: this.form
      })
      .then( user => {
        this.$auth.setUser(user.data)
      })
      .catch( err => {
        console.error(err)
      })
    }
  }
}
</script>
