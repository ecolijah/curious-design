<script setup>

import {ref} from "vue";

//selected index
var selectedIndex =  ref(1);

function traverse(option) {

    switch(option) {
        //next
        case 0:
            if (selectedIndex.value !=4)
                selectedIndex.value += 1;
            break;
        case 1:
            if (selectedIndex.value !=1)
                selectedIndex.value -= 1;
            break;
    }
    console.log("selectedIndex: " + selectedIndex.value)

}


</script>

<template>

    <div class="container">

        <div class="top-spacer"></div>

        <div class="image-spacer">
            <div class="image-container">
                <button class="back" @click="traverse(1)"></button>
                <button class="forward" @click="traverse(0)"></button>
                <img v-show="selectedIndex==1"src="./piece-assets/bloc-table/1.JPG" alt="bloc-table">
                <img v-show="selectedIndex==2"src="./piece-assets/bloc-table/2.JPG" alt="bloc-table">
                <img v-show="selectedIndex==3"src="./piece-assets/bloc-table/3.JPG" alt="bloc-table">
                <img v-show="selectedIndex==4"src="./piece-assets/bloc-table/4.JPG" alt="bloc-table">
                
            </div>
            <div class="caption">
                <h3>bloc table</h3>
                <h5>white birch plywood, concrete         (2023)</h5>
                <h5>(20"x30"x14")</h5>
                <h5>©</h5>
            </div>
        </div>

        
    </div>
    
</template>

<style scoped>

    .top-spacer {
        display: flex;
        min-height: 15vh;
        max-height: 15vh;
        /* background-color: blue; */
    }
    .image-spacer {
        display: flex;
        min-height: 65vh;
        max-height: 65vh;
        /* background-color: yellowgreen; */
        align-items: flex-start;
        justify-content: center;
        flex-direction: column;
        width: 100%;
    }

    .caption {
        display: flex;
        width: inherit;
        justify-content: space-between;
        align-items: baseline;
        /* background-color: aqua; */
    }

    .container {

        display:  flex;
        flex-direction: column;      
        /* background-color: greenyellow; */
        padding-left: 80px;
        padding-right: 80px;
        max-height: 100vh;
        min-height: 100vh;
 
    }

    .image-container {
    display: flex;
    position: relative;
    align-items: center;
    justify-content: center;
    max-width: 2000px;
    max-height: 65vh; /* Set max-height to the height of image-spacer */
    }

    .back {
        position: absolute;
        left: 0;
        width: 30%;
        height: 100%;
        /* background-color: antiquewhite; */
    }
    .forward {
        position: absolute;

        right: 0;
        width: 30%;
        height: 100%;
        /* background-color: antiquewhite; */
    }

    .image-container img {
        max-width: 100%; /* Ensures the image doesn't exceed the width of its container */
        max-height: 65vh; /* Ensures the image doesn't exceed the height of its container */
        width: auto;
        height: auto;
        border-radius: 6px;

    }

    .nav {
        display: flex;
        justify-content: flex-start;
        align-items: baseline;
        /* background-color: brown; */
        min-height: 20vh;
        max-height: 20vh;
        color: #3a3a3a;
        
        gap: 16%;
        margin-top: -10px;
    }
    .nav h3 {
        font-weight: 500;
        font-size: 12pt;
    }

    h5 {
        font-weight: 400;
        font-size: 10pt;
        color: #3a3a3a;
    }


    button {
        background: none; /* Removes background color */
        border: none; /* Removes border */
        margin: 0; /* Removes margin */
        cursor: pointer; /* Adds pointer cursor */
    }

</style>