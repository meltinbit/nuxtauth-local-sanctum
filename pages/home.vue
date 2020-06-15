<template>
  <div>
    <h1>Home</h1>
    <div v-if="$auth.loggedIn">
      Welcome {{  $auth.user.name }}
      <button @click="$auth.logout()">Logout</button>
    </div>
    <div v-else>
      Devi prima accedere <nuxt-link to="/login">Login</nuxt-link>
    </div>
  </div>
</template>

<script>


export default {
  
}
</script>
