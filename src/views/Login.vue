<template>
  <div class="container">
    <br>
    <div class="box">
      <h2 class="is-size-4 has-text-centered">Login</h2>
      <hr class="hr">
      <form @submit.prevent="login({ username, password})" class="form">
        <div class="field">
          <label class="label">Username</label>
          <div class="control">
            <input v-model="username" class="input" type="text" placeholder="homerjsimpson">
          </div>
        </div>
        <div class="field">
          <label class="label">Password</label>
          <div class="control">
            <input v-model="password" class="input" type="password" placeholder="super secure password">
          </div>
        </div>
        <div class="field is-grouped">
          <div class="control">
            <button class="button is-link" type="submit">Submit</button>
          </div>
          <div class="control">
            <a class="button is-light" href="/signup">Sign up</a>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'home',
  data () {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    login () {
      this.$store.dispatch('login', {
        username: this.username,
        password: this.password
      }).then(() => {
        this.$router.push('/')
      })
    }
  }
}
</script>
