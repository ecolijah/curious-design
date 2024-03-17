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
    <div class="sidebar-container">

        <div class="logo">
            <h1>curious</h1>
            <h2>design studio</h2>
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

        <div class="content">
            <About v-if="showAbout" />
            <Contact v-if="showContact" />
            <BlocTable v-if="showBlocTable" />
            <DvdCabinet v-if="showDvdCabinet" />
        </div>

    </div>

    
</template>

<style scoped>
</style>