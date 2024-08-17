<template>
    <div id="container1">
        <Header />
        <h1>Hello user, Welcome to the Add restaurant page</h1>
        <form class="add">
            <input type="text" name="name" placeholder="Enter Name" v-model="restaurant.name"/>
            <input type="text" name="adresse" placeholder="Enter Adresse" v-model="restaurant.address" />
            <input type="text" name="contact" placeholder="Enter contact" v-model="restaurant.contact"/>
            <button class="addbutton" v-on:click="AddRestaurant" type="button">Add new restaurant</button>
        </form>
    </div>
</template>

<script>
    import Header from './Header.vue'
    import axios from 'axios';
    export default{
        name:'Add',
        data(){
            return{
                restaurant:{
                    name:'',
                    contact:'',
                    address:''
                }
            }
        },
        methods:{
            async AddRestaurant(){
                console.warn(this.restaurant)
                const result = await axios.post("http://localhost:3000/restaurants",{
                    name:this.restaurant.name,
                    contact:this.restaurant.contact,
                    address:this.restaurant.address,
                })
                if(result.status==201){
                    this.$router.push({name:'Home'})
                }
                console.warn(result);
            }
        },
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