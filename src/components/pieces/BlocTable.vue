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
            <h5>birch plywood and concrete</h5>

            <div>
                <button @click="traverse(1)"><</button>
                <button @click="traverse(0)">></button>
            </div>

            <div>
                <h5>birch plywood and concrete</h5>
            </div>
            

        </div>
        
    </div>
    
</template>

<style scoped>

    .container {
        display:  flex;
        flex-direction: column;
        object-fit: contain; /*Maintain aspect ratio and fit within the container*/
        margin: 0 auto;
        gap: 0px;
 
    }

    .image-container {
        display:  flex;
        /* flex-direction: column; */
        /* height: 90vh; */
        /* object-fit: contain; */
        align-items: center;
        /* justify-content: flex-start; */
        /* background-color: red; */
        height: 87vh;
       
    }
    .nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        /* background-color: blue; */
        height: 5vh;
    }

    img {
        /* width: 1920px; */
        /* height: 90vh; */
        max-width: 100%; /* Maximum width of the image */
        max-height: 100%; /* Maximum height of the image */
        object-fit: contain; /*Maintain aspect ratio and fit within the container*/

    }
    h5 {
        padding: 0;
    }

</style>