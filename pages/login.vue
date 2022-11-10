<template>
    <div class="p-5 login-box">
        <h2>Login</h2>
        <input type="text" v-model="username" placeholder="Username" class="m-2"> <br>
        <input type="password" v-model="password" placeholder="Password" class="m-2"> <br>
        <button v-on:click="getToken" class="m-2 bg-dark text-white">Submit</button>
        <button v-on:click="logout" class="m-2 bg-dark text-white">Logout</button>
        <p>{{successMessage}}</p>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                username: '',
                password: '',
                successMessage: ''
            }
        },
        methods: {
            getToken() {
                this.$axios.post('https://blogbackend.malavikasmenon.repl.co/api-token-auth/', {
                    'username': this.username,
                    'password': this.password,
                })
                    .then(response => {
                        console.log(response.data)
                        if(process.client){
                            localStorage.setItem("authToken", response.data.token);
                        }
                        // this.$cookies.set("token", response.data.token)
                        this.successMessage = "Successfully logged in"
                    })
                    .catch(error => console.log(error))
            },
            logout() {
                if(process.client){
                    localStorage.removeItem('authToken')
                    this.successMessage = "Logged Out"
                }
            }
        },
    }
</script>

<style  scoped>
.login-box {
    border: 1px solid black;
    border-radius: 10px;
    margin: auto;
    max-width: 30%;
    text-align: center;
}
</style>