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

        <div class="image-container">
            <img v-if="selectedIndex==1"src="./piece-assets/bloc-table/1.JPG" alt="bloc-table">
            <img v-if="selectedIndex==2"src="./piece-assets/bloc-table/2.JPG" alt="bloc-table">
            <img v-if="selectedIndex==3"src="./piece-assets/bloc-table/3.JPG" alt="bloc-table">
            <img v-if="selectedIndex==4"src="./piece-assets/bloc-table/4.JPG" alt="bloc-table">
        </div>

        
        
        <div class="nav">
            <h5>white birch plywood, concrete</h5>

            <div>
                <button @click="traverse(1)"><</button>
                <button @click="traverse(0)">></button>
            </div>

            <!-- <div>
                <h5>white birch plywood, concrete</h5>
            </div> -->
            

        </div>
        
    </div>
    
</template>

<style scoped>

    .container {

        display:  flex;
        flex-direction: column;      
        /* background-color: greenyellow; */
        padding: 80px;
 
    }

    .image-container {

        display:  flex;
        align-items: center;
        max-width: 2000px;
        min-width: 600px;
   
       
    }
    .nav {
        display: flex;
        justify-content: flex-start;
        align-items: baseline;
        /* background-color: blue; */
        height: 5vh;
        color: #3a3a3a;
        
        gap: 33%;
    }

    h5 {
        font-weight: 400;
        font-size: 10pt;
        color: #3a3a3a;
    }

    img {
        max-width: 100%; /*correct*/
        max-height: 100%; 
        object-fit: contain; /*Maintain aspect ratio and fit within the container*/

    }

    button {
        background: none; /* Removes background color */
        border: none; /* Removes border */
        padding: 20px; /* Removes padding */
        margin: 0; /* Removes margin */
        cursor: pointer; /* Adds pointer cursor */
    }

</style>