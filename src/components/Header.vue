<template>
    <div id="container">
        <a href="#">Home</a>
        <a href="#">Add Restaurant</a>
        <a href="#">Update Restaurant</a>
        <a href="#">Logout</a>
    </div>
</template>

<script>
    export default {
        name: 'Header',
    }
</script>

<style>
body {
    background-color: black;
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
    background-size: 100% 99%;
    background-position: center;
    filter: blur(8px); /* Adds blur to the background image */
    z-index: -1; /* Places the blurred image behind the content */
}

#container {
    background-color: aqua;
    opacity: 30%;
    width: 100%;
    height: 50px;
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 30px;
    border-radius: 30px;
    position: relative;
    z-index: 1; /* Ensures the header is above the blurred background */
}

#container a {
    text-decoration: none;
}
</style>
