<template>
    <div id="app">
        <div class="container">
            <div class="row margen">
                <div v-if="loginok" class="col-sm-6 offset-sm-3">
                <form>
                  <div class="form-group">
                      <label for="username">Username</label>
                      <input type="text" v-model="username" name="username" class="form-control" />
                  </div>
                  <div class="form-group">
                      <label htmlFor="password">Password</label>
                      <input type="password" v-model="password" name="password" class="form-control" />
                  </div>
                </form>
                  <button type="button" class="btn btn-success" @click="registro()">Register</button>
                  <button type="button" class="btn btn-success" @click="userlogin()">Login</button>
                </div>
                <div v-if="registerok" class="col-sm-6 offset-sm-3">
                  <UserRegister />
                </div>
                <div v-if="producsok">
                  <ListProducts />
                </div>
            </div>
        </div>
    </div>
</template>
<script>

import UserRegister from './components/UserRegister.vue';
import ListProducts from './components/ListProducts.vue';

export default {
    name: 'app',

    data() {
      return{
      loginok: true,
      registerok: false,
      producsok: false,
      username: '',
      password: '',
      }
    },

    components: {
    UserRegister,
    ListProducts
},

  methods: {

    registro() {
      this.registerok = true;
      this.loginok = false;
    },
    userlogin(){
            this.users = JSON.parse(localStorage.getItem("users"));
            console.log(this.users[0].pass);
            if (this.users[0].pass == this.password) {
                this.producsok = true;
                this.loginok = false;
            }
            else{
                this.loginok = true;
                alert("Contraseña incorrecta")
            }
    }
            
  }

};
</script>

<style>
  .margen{
    margin-top: 10rem;
  }
</style>