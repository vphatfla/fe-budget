<template>
  <div class="col-12 h-100 row container d-flex align-items-center m-0" style="min-width: 100%">
    <div class="col col-6 text-center">
      <h2>Login</h2>
    </div>
    <div class="col col-6 text-center">
      <div style="max-width: 300px">
        <form @submit.prevent="login">
          <input v-model="username" class="mb-2" label="User Name" />
          <input v-model="password" class="mt-2" label="Password" type="password" />
          <div class="h-5 mt-2"></div>
          <button class="btn btn-primary" on-click="login">Log In</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { loginFunction } from '../auth/authService'
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Login',
  data() {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    async login() {
      console.log('Login Handler')
      const res = await loginFunction(this.username, this.password)
      if (res === null) {
        console.log('log in successed')
        const user_id = localStorage.getItem('user_id') || ''
        console.log('user id = ', +user_id)
        this.$router.push({
          path: '/transactions',
          query: { userId: user_id }
        })
      } else {
        console.log(res)
      }
    }
  }
}
</script>
