<script setup>
//import gsap from "gsap";
//import ScrollTrigger from "gsap/ScrollTrigger";
//import { ref } from 'vue';
</script>

<template>
    <div class="container-fluid p-0">
        <div class="jumbotron text-white jumbotron-image shadow">
            <div class="wrapper">
                <h1 class="display-1 mb-4"><div class="e">E</div><div class="first-v">V</div><div class="second-v">V</div><div class="a">A</div><div class="b">B</div></h1>
            </div>
            <p class="mb-4">Hey, check this out.</p>
            <a class="btn btn-primary">Click!</a>
        </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@800&display=swap');
@font-face {
    font-family: 'BigNoodleTitling';
    src:url('../assets/BigNoodleTitling.ttf.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}

    .jumbotron {
        background-image: url('../assets/jumbotron-bg.jpg');
        height: 70vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-size: cover;
        background-repeat: no-repeat;
    }
    .wrapper {
        position: relative;
        width: 100vw;
    }
    .jumbotron h1 {
        font-family: 'Montserrat', sans-serif;
        color: #E74D14;
        -webkit-transform:scale(1,3);
        -moz-transform:scale(1,3); 
        -ms-transform:scale(1,3); 
        -o-transform:scale(1,3); 
        transform:scale(1,3);
    }
    .e {
        position: absolute;
        left:0;
        right:0;
        margin-left:-80px;
    }
    .first-v {
        position: absolute;
        left:0;
        right:0;
        margin-left:auto;
        margin-right:auto;
        color: #212529;
        z-index: 1;
    }
    .second-v {
        position: absolute;
        left: 0;
        right: 0;
        margin-left: 30px;
        z-index: -1;
    }
    .a {
        position: absolute;
        left: 0;
        right: 0;
        margin-left: 80px;
    }
    .b {
        position: absolute;
        left: 0;
        right: 0;
        margin-left: 180px;
    }
</style>