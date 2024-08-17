<template>
    <div id="container1">
        <Header />
        <h1>Hello {{name}}, Welcome to the user page</h1>
        <table >
            <tr>
                <td class="Title">Id</td>
                <td class="Title">Name</td>
                <td class="Title">Contact</td>
                <td class="Title">Address</td>
            </tr>
            <tr v-for="item in restaurant" :key="item.id">
                <td class="restaurant">{{ item.id }}</td>
                <td class="restaurant">{{ item.name }}</td>
                <td class="restaurant">{{ item.contact }}</td>
                <td class="restaurant">{{ item.address }}</td>
            </tr>
        </table>
    </div>
</template>

<script>
    import Header from './Header.vue'
    import axios from 'axios';
    export default{
        name:'Home',
        data(){
            return{
                name:'',
                restaurant:[]
            }
        },
        components:{
            Header
        },
        async mounted(){
        let user = localStorage.getItem('user-info');
        this.name = JSON.parse(user).name
        if(!user){
            this.$router.push({name:'SignUp'})
        }

        let result = await axios.get("http://localhost:3000/restaurants");
        this.restaurant=result.data;

    }
    };
</script>

<style>
    #container1{
        align-items: center;
        display: flex;
        flex-direction: column;
    }
    td{
        width: 200px;
        height: 40px;
        margin: 3px;
        border-radius: 50%;      
    }
    .Title{
        color: rgb(255, 255, 255);
        background-color: rgba(255, 0, 0, 0.422);
        text-align: center;
    }
    table{
        text-align: center;
        color: rgb(255, 255, 255); 
        
    }
    .restaurant{
        background-color: rgba(40, 255, 2, 0.455);
    }
</style>