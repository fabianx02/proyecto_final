<template>
    <div>
        <h2>Register</h2>
        <form>
            <div class="form-group">
                <label for="firstName">Nombre</label>
                <input type="text" v-model="nombre" name="firstName" class="form-control" />
                
            </div>
            <div class="form-group">
                <label for="lastName">Apellido</label>
                <input type="text" v-model="apellido" name="lastName" class="form-control" />
                
            </div>
            <div class="form-group">
                <label for="username">Username</label>
                <input type="text" v-model="username" name="username" class="form-control" />
                
            </div>
            <div class="form-group">
                <label htmlFor="password">Password</label>
                <input type="password" v-model="pass" name="password" class="form-control" />
                
            </div>
            <div class="form-group">
                <button class="btn btn-primary" @click="guardar">Register</button>
            </div>
        </form>
    </div>
</template>

<script>


export default {
    data () {
        return {
            user: {
                nombre: '',
                apellido: '',
                username: '',
                pass: '',
            },
            nuevoArray: [],
            submitted: false
        }
    },
    computed: {

    },
    methods: {
    guardar() {
        var user= {
                nombre: this.nombre,
                apellido: this.apellido,
                username: this.username,
                pass: this.pass
            };

        this.nuevoArray.push(user);
        const parsed = JSON.stringify(this.nuevoArray);
        localStorage.setItem('users', parsed);
    }
    }
};
</script>