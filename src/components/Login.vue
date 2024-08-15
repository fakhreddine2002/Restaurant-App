<template>
    <div class="container">
        <img class="logo" src="../assets/the-red-cafe.jpg" alt="">
        <h1>Login</h1>
        <div class="register">
            <input type="text" v-model="email" placeholder="Enter Email">
            <input type="password" v-model="password" placeholder="Enter Password">
            <button v-on:click="Login">login</button>
           
        </div>
        <p><router-link id="login" to="/sign-up" >sign up</router-link></p>
    </div>
</template>

<script>
import axios from 'axios';
export default{
    name:'Login',
    data(){
        return{
            email:'',
            password:''

        }
    },
    methods:{
        async Login(){
            let result = await axios.get(
                `http://localhost:3000/user?${this.name}&password=${this.password}`
            )
            if(result.status==200 && result.data.length==1){
                alert("login successfully")
                localStorage.setItem("user-info",JSON.stringify(result.data[0]))
                this.$router.push({name:'Home'})
            }else{
                alert("check again")
            }
            console.warn(result)
        }
    },  
    mounted(){
        let user = localStorage.getItem('user-info');
        console.log(user);
        if(user){
            this.$router.push({name:'Home'})
        }
    }
    
}
</script>
