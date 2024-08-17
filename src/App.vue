<script>
  export default{
    name:'App'
  }
</script>

<template>
  <router-view /> 
</template>

<style>
    .logo{
        width: 250px;
    }
    .register input , .add input {
        width: 300px;
        height: 40px;
        padding-left: 20px;
        display: block;
        margin-bottom: 30px;
        margin-right: auto;
        margin-left: auto;
        border : 1px solid skyblue;
    }
    .register button:hover,.addbutton:hover{
        background-color: blue;
    }
    .register button , .addbutton{
        width: 320px;
        height: 40px;
        border: 1px solid skyblue;
        background: skyblue;
        color : white;
        cursor : pointer;
        transition: background-color 0.3s ease;
        /* margin-left: 608px; */
    }
    .container{
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px;
    }
    h1{
        font-family: 'Times New Roman', Times, serif;
        font-size:xx-large;
    }
    #login{
        text-decoration: none;
        color: black;
    }
</style>
