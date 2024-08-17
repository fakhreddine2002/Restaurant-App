<template>
    <div id="container">
        <router-link to="/">Home</router-link>
        <router-link to="/add">Add Restaurant</router-link>
        <router-link to="/update">Update Restaurant</router-link>
        <a v-on:click="logout" href="#">Logout</a>
    </div>
</template>

<script>
    export default {
        name:'Header',
        methods:{
            logout()
            {
                localStorage.clear();
                this.$router.push({name:"Login"})
            }
        }
    }
</script>

<style>
body {
    margin: 0;
    padding: 0;
    position: relative;
    height: 100vh;
    overflow: hidden;
}

body::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: url("/restaurant image.jpg");
    background-repeat: no-repeat;
    background-size: 100% 110%;
    background-position: center;
    filter: blur(5px);
    z-index: -1;
}

#container {
    margin-top: 20px;
    width: 50%;
    height: 50px;
    display: flex;
    border: 3px solid white;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 60px;
    border-radius: 30px;
    position: relative;
    z-index: 1;
    transition: color 1s ease-in-out; /* Smooth transition for border gradient */
}

#container:hover {
    border-radius: 30px;
    border-color: aqua; /* Gradient effect on border */
}

#container a {
    text-decoration: none;
    color: white;
    transition: color 0.4s ease-in-out; /* Smooth transition for text color */
}

#container a:hover {
    color: red;
}
</style>
