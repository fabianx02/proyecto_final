<template>
    <div>
        <h2>Login</h2>
        <form>
            <div class="form-group">
                <label for="username">Username</label>
                <input type="text" v-model="username" name="username" class="form-control" :class="{ 'is-invalid': submitted && !username }" />
            </div>
            <div class="form-group">
                <label htmlFor="password">Password</label>
                <input type="password" v-model="password" name="password" class="form-control" :class="{ 'is-invalid': submitted && !password }" />
            </div>
            <button type="button" class="btn btn-success" @click="userlogin()">Login</button>
        </form>
    </div>
</template>

<script>

export default {
    data () {
        return {
            username: '',
            password: '',
            submitted: false,
            vistas: true,
        }
    },

    created () {
        
        
    },

    methods: {
        userRegister() {

        },

        UserVerificated() {

            

        },

        userlogin() {
                        this.users = JSON.parse(localStorage.getItem("users"));
                        console.log(this.users);
                        if (this.users.pass == "123") {
                            alert("message");
                        }
                        else{
                            alert("message2");
                        }
                    }
            },
           
    }
</script>

