<template>
  <div>
    <h1>Registration</h1>
    <label>E-mail</label>
    <input
      type="email"
      v-model="email"
      name="email"
      id="emailid"
      placeholder="email"
    />
    <br />
    <label>Password</label>
    <input
      type="password"
      v-model="password"
      name="password"
      id="passid"
      placeholder="password"
    />
    <br />
    <button @click="register">Submit</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: 'surea',
      password: 'surea'
    }
  },
  // watch: {
  //   email (val) {
  //     console.log('email is changed', val)
  //   }
  // },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log('Registered!', response.data)
    }
  }
  // mounted () {
  //   setTimeout(() => {
  //     this.email = 'timeout'
  //   }, 5000)
  // }
}
</script>
<style scoped></style>
