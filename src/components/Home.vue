<template>
    <div id="container1">
        <Header />
        <h1>Hello user, Welcome to the user page</h1>
    </div>
</template>

<script>
    import Header from './Header.vue'
    export default{
        name:'Home',
        components:{
            Header
        },
        mounted(){
        let user = localStorage.getItem('user-info');
        if(!user){
            this.$router.push({name:'SignUp'})
        }
    }
    };
</script>

<style>
    #container1{
        align-items: center;
        display: flex;
        flex-direction: column;
    }
</style>