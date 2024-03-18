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

    <div class="image-container">
        <img src="./piece-assets/bloc-table/4.JPG" alt="bloc-table">
        
        
        <div class="nav">

            <button @click="traverse(1)">last</button>
            <button @click="traverse(0)">next</button>

        </div>
        
    </div>
    
</template>

<style scoped>

    .image-container {
        display:  flex;
        flex-direction: column;
        height: 95vh;
        /* object-fit: contain; */
        /* align-items: center; */
       
    }
    .nav {
        display: flex;
        justify-content: center;
    }

    img {
        /* width: 1920px; */
        /* height: 90vh; */
        max-width: 100%; /* Maximum width of the image */
        max-height: 100%; /* Maximum height of the image */
        object-fit: contain; /*Maintain aspect ratio and fit within the container*/

    }

</style>