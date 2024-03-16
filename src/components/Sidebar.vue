<script setup>
//import all components to be rendered here
import {ref} from "vue";
import About from "./About.vue";
import Contact from "./Contact.vue";

var showAbout =  ref(false);
var showContact =  ref(false);

function toggleView(option) {
    //ideally pass argument for reusable function
    console.log("button pressed.")

    switch (option) {
        case 0:
            //about
            if (showAbout.value == false)
                showAbout.value = !showAbout.value;
                showContact.value =  false;
                break;
            
        case 1:
            //contact card
            if (showContact.value == false)
                showContact.value = !showContact.value;
                showAbout.value = false;
                break;

    }
}

</script>

<template>
    <div class="sidebar-container">

        <div class="logo">
            <h1>curious</h1>
            <h2>design studio</h2>
        </div>

        <div class="buttons">
            <ul>
                <li>dvd cabinet</li>
                <li>bloc table</li>
            </ul>
        </div>

        <div class="buttons-2">
            <ul>
                <button @click="toggleView(0)">about</button>
                <button @click="toggleView(1)">contact</button>
            </ul>
        </div>
        <div v-if="showAbout">
            <!-- <About v-if="showAbout" /> -->
            <About />
        </div>
        <Contact v-if="showContact" />


    </div>

    
</template>

<style scoped>
</style>