<template>
    <div>
        <h1>Train</h1>
        <form action="">
             <label for="name">Name</label>

            <input 
            type="text"
            name="name" 
            id="name"
            v-model="name">

             <label for="email">Email</label>

            <input 
            type="email" 
            name="email" 
            id="email"
            v-model="email">

            <label for="password">Password</label>
            <input 
            type="password" 
            name="password" 
            id="password"
            v-model="password">
            <label for="passwordConf">Confirm password</label>
            <input 
            type="password" 
            name="passwordConf" 
            id="passwordConf"
            v-model="passwordConf">
            <button @click.prevent="register">Register</button>
        </form>
        
        
    </div>
</template>

<script>
import AuthService from '@/services/AuthService'
    export default {
        data(){
            return{
                name:'',
                email:'',
                password:'',
                passwordConf:''
            }
        },
        watch:{
            
        },
        mounted(){
            
        },
        methods:{
            async register(){
                const response = await AuthService.register({
                    name: this.name,
                    email: this.email,
                    password: this.password
                })
                console.log(response.data, '')
                
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>