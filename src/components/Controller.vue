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
const isDarkMode = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;

var showMobileMenu =  ref(false);
function toggleMobileMenu() {
        showMobileMenu.value = !showMobileMenu.value;
        console.log("isdark: " + isDarkMode)

    }
    
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
                showMobileMenu.value = false;
                break;
            
        case 1:
            //contact card
            if (showContact.value == false)
                showContact.value = true;
                showAbout.value = false;
                showDvdCabinet.value = false;
                showBlocTable.value = false;
                showMobileMenu.value = false;
                break;
        case 2:
            if (showBlocTable.value == false)
                showBlocTable.value =  true;
                showDvdCabinet.value = false;
                showContact.value = false;
                showAbout.value = false;
                showMobileMenu.value = false;
                break;
        case 3:
            if (showDvdCabinet.value == false)
                showDvdCabinet.value =  true;
                showBlocTable.value = false;
                showContact.value = false;
                showAbout.value = false;
                showMobileMenu.value = false;
                break;       

    }
}

</script>

<template>
    <div class="controller-container">

        <div class="sidebar">

            <div class="logo">
                <img v-show="!isDarkMode" src="../assets/finall.svg" alt="logo"/>
                <img v-show="isDarkMode" src="../assets/finall-white.svg" alt="logo"/>
            </div>

            <div class="buttons">
                <ul>
                    <button @click="toggleView(2)" :class="{ selected: showBlocTable }">bloc table</button>
                    <button @click="toggleView(3)" :class="{ selected: showDvdCabinet }">dvd cabinet</button>
                    <!-- <button @click="toggleView(2)" >book trough</button>
                    <button @click="toggleView(2)" >cat dome</button> -->
                </ul>
            </div>

            <div class="buttons-2">
                <ul>
                    <button @click="toggleView(0)" :class="{ selected: showAbout }">about</button>
                    <button @click="toggleView(1)" :class="{ selected: showContact }">contact</button>
                    
                </ul>
            </div>

        </div>

        <div class="mobile-menu">
            <div class="logo">
                <button @click="toggleMobileMenu">
                    <img v-show="!isDarkMode" src="../assets/finall.svg" alt="logo"/>
                    <img v-show="isDarkMode" src="../assets/finall-white.svg" alt="logo"/>
                </button>
                
            </div>
            <ul class="bullets" :class="{ 'show': showMobileMenu }">
                <button @click="toggleView(2)" :class="{ selected: showBlocTable }">bloc table</button>
                <button @click="toggleView(3)" :class="{ selected: showDvdCabinet }">dvd cabinet</button>
                <button @click="toggleView(0)" :class="{ selected: showAbout }">about</button>
                <button @click="toggleView(1)" :class="{ selected: showContact }">contact</button>
            </ul>
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
/* Ensure .mobile-menu is hidden for widths larger than 800px */
@media only screen and (min-width: 801px) {
    .mobile-menu {
        display: none;
    }
    img {
        /* margin-top: 40%; */
        max-width: 65%; /* Maximum width of the image */
        max-height: 65%; /* Maximum height of the image */
        object-fit: contain; /*Maintain aspect ratio and fit within the container*/
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
        font-weight: 400;
        font-family: inherit;
        cursor: pointer;
        color: var(--menu-button-color);
    }
    .logo {
        display: flex;
        justify-content: center;
        align-items:center;
        /* background-color: bisque; */
        /* padding-left: 45px;
        padding-right: 20px; */

        height: 15vh;
        /* min-height: 70px;
        min-width: 183px; */

    }

}

@media only screen and (max-width: 800px) {

    .logo {
        margin-top: 10px;
    }

    button {
        text-align: center;
        border: none;
        background-color: var(--content-bg-color);

        cursor: pointer;

        /* background-color: #9FCB85; */
    }
    .sidebar {
        display: none;
    }

    .mobile-menu {
        /* top: 50px; */
        position: absolute;
        width: 100%;
        height: auto;
        z-index: 1;
        /* background-color: #ffffff; */
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-color: var(--content-bg-color);

    }

    .mobile-menu img {

        /* background-color: red; */
        /* height: 100px; */

        width:40%;
        margin: 0;
        z-index: 999;

    }
    .controller-container {
        flex-direction:  column;
    }
}

    .bullets {
        margin-top: 0;
        max-height: 0;
        width: 100%;
        overflow:hidden;
        transition: max-height 0.5s ease-in-out;
        margin-bottom: 10px;
        /* background-color: #bddd9462; */
        background-color: var(--content-bg-color);



        padding-right: 50px;
 
    }

    .bullets button {
        margin-top: 10px;
    }

.bullets.show {
    max-height: 1000px; /* Adjust this value to fit your content */
    display: flex;
    align-items: center;
    padding-right: 50px;
}


    .controller-container {
        display: flex;
        /* flex-direction: row; */
        justify-content: flex-start;
        /* background-color: blue; */
        height: 100vh;
    }

    .sidebar {
        /* display: flex; */
        flex: 0;
        flex-direction: column;
        /* background-color: rgb(243, 246, 243); */
     
        min-width: 250px;
        /* justify-content: flex-end; */
    }




    .buttons {
        display: flex;
        min-height: 65vh;
        justify-content: flex-start;
        align-items: flex-start;
        padding-left: 15px;
        
        /* background-color: blueviolet; */
        
        
    }

    .buttons button {
        transition: color 0.3s ease;

    }

    .buttons button:hover {
        color: var(--accent-color);
        


    }
    .buttons-2 button:hover {
        color: var(--accent-color);

    }

    .buttons-2 button {
        transition: color 0.3s ease;
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
        background-color: var(--content-bg-color);
    }
    ul {
        display: flex;
        flex-direction: column;
    }



    .selected {
        color: var(--p-color);
        text-decoration: line-through;
        
    }

</style>