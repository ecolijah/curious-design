<script setup>
//import all components to be rendered here
import {ref} from "vue";
import About from "./About.vue";
import Contact from "./Contact.vue";
import BlocTable from "./pieces/BlocTable.vue"
import DvdCabinet from "./pieces/DvdCabinet.vue";
//utility: onmount is false
var showAbout =  ref(false);
var showContact =  ref(false);

//pieces: onmount is true for firts impression
var showBlocTable =  ref(true);
var showDvdCabinet =  ref(false);

function toggleView(option) {
    //ideally pass argument for reusable function
    console.log("button pressed.")

    switch (option) {
        case 0:
            //about
            if (showAbout.value == false)
                showAbout.value = true;
                showContact.value =  false;
                showDvdCabinet.value = false;
                showBlocTable.value = false;
                break;
            
        case 1:
            //contact card
            if (showContact.value == false)
                showContact.value = true;
                showAbout.value = false;
                showDvdCabinet.value = false;
                showBlocTable.value = false;
                break;
        case 2:
            if (showBlocTable.value == false)
                showBlocTable.value =  true;
                showDvdCabinet.value = false;
                showContact.value = false;
                showAbout.value = false;
                break;
        case 3:
            if (showDvdCabinet.value == false)
                showDvdCabinet.value =  true;
                showBlocTable.value = false;
                showContact.value = false;
                showAbout.value = false;
                break;       

    }
}

</script>

<template>
    <div class="controller-container">

        <div class="sidebar">

            <div class="logo">
                <img src="../assets/curious-logo.png" alt="logo"/>
            </div>

            <div class="buttons">
                <ul>
                    <button @click="toggleView(3)">dvd cabinet</button>
                    <button @click="toggleView(2)">bloc table</button>
                </ul>
            </div>

            <div class="buttons-2">
                <ul>
                    <button @click="toggleView(0)">about</button>
                    <button @click="toggleView(1)">contact</button>
                </ul>
            </div>

        </div>
        

        <div class="content">
            <About v-show="showAbout" />
            <Contact v-show="showContact" />
            <BlocTable v-if="showBlocTable" />
            <DvdCabinet v-if="showDvdCabinet" />
        </div>

    </div>
    
</template>

<style scoped>

    .controller-container {
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
        /* background-color: blue; */
        height: 100vh;
    }

    .sidebar {
        display: flex;
        flex: 0;
        flex-direction: column;
        /* background-color: lightgreen; */
     
        min-width: 250px;
        /* justify-content: flex-end; */
    }

    .logo {
        display: flex;
        justify-content: baseline;
        align-items:flex-end;
        /* background-color: bisque; */
        padding-left: 45px;

        height: 15vh;
        min-height: 70px;
        min-width: 183px;

    }

    img {
        max-width: 100%; /* Maximum width of the image */
        max-height: 100%; /* Maximum height of the image */
        object-fit: contain; /*Maintain aspect ratio and fit within the container*/
    }

    .buttons {
        display: flex;
        min-height: 65vh;
        justify-content: flex-start;
        align-items: flex-start;
        padding-left: 15px;
        /* background-color: blueviolet; */
        
        
    }

    .buttons-2 {
        min-height: 20vh;
        display: flex;
        justify-content: flex-start;
        align-items: flex-start;
        padding-left: 15px;

        /* background-color: red; */
    }

    .content {
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;
        /* background-color: brown; */
    }
    ul {
        display: flex;
        flex-direction: column;
    }
    button {
        /* width: 100px; */
        display: flex;
        height: 30px;
        background: none; /* Removes background color */
        border: none; /* Removes border */
        padding: 0; /* Removes padding */
        margin: 0; /* Removes margin */
        cursor: pointer; /* Adds pointer cursor */
        text-align: left; /* Aligns text to the left */
        font-size: 10pt;
        font-weight: 500;
        font-family: inherit;
        cursor: pointer;
        color: #3a3a3a;
    }

</style>