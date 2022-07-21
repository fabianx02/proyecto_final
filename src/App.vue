<template>
    <div id="app">
        <div class="container">
            <div class="row margen">
                <div v-if="vistas" class="col-sm-6 offset-sm-3">
                  <LoginUser />
                  <button type="button" class="btn btn-success" @click="registro()">Register</button>
                </div>
                <div v-else class="col-sm-6 offset-sm-3">
                  <UserRegister />
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import LoginUser from './components/LoginUser.vue'
import UserRegister from './components/UserRegister.vue';
export default {
    name: 'app',

    data() {
      return{vistas: true}
    },

    components: {
    LoginUser,
    UserRegister
},

  methods: {

    registro() {
        this.vistas = false;
    }
            
  }

};
</script>

<style>
  .margen{
    margin-top: 10rem;
  }
</style>