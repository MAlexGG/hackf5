<template>
  <h1 class="my-5 d-flex justify-content-center">Ingreso de Usuario</h1>
  <form @submit.prevent="loginForm">
    <div class="container">
      <div class="form-group my-4">
        <label for="email">Email</label>
        <input type="email" placeholder="Introduce Email" class="form-control" id="email" v-model.trim="email">
      </div>
      <div class="form-group my-4">
        <label for="password">Contraseña</label>
        <input type="password" placeholder="Password" class="form-control" id="password" v-model.trim="pass">
      </div>
      <router-link to="/" type="submit" class="btn btn-primary btn-block" :disabled="btnBlock">Entrar</router-link>
    </div>
  </form>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      email: 'hackf5@gmail.com',
      pass: '123123',
    }
  },
  computed: {
    btnBlock() {
      if(!this.email.includes('@') && (!this.email.includes('.'))){
        return true
      }
      if((this.pass.length > 5)){
        return false
      }
      return true
    },
  },
  methods: {
    loginForm(){
      console.log('Logueando')
    }
  }
}
</script>

<style scoped>

</style>