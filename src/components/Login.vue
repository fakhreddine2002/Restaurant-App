<template>
    <div class="container">
        <img class="logo" src="../assets/the-red-cafe.jpg" alt="">
        <h1>Login</h1>
        <div class="register">
            <input type="text" v-model="email" placeholder="Enter Email">
            <input type="password" v-model="password" placeholder="Enter Password">
            <button v-on:click="signUp">login</button>
           
        </div>
        <p><router-link id="login" to="/sign-up" >sign up</router-link></p>
    </div>
</template>

<script>
export default{
    name:'Login'
}
</script>
