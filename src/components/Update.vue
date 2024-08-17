<template>
    <div id="container1">
        <Header />
        <h1>Hello user, Welcome to the update user page</h1>
    </div>
</template>

<script>
    import Header from './Header.vue'
    export default{
        name:'Update',
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