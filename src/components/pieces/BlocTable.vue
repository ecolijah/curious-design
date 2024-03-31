<script setup>

import {ref} from "vue";

//selected index
var selectedIndex = ref(1);

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
                <h5>white birch plywood, concrete (2023)</h5>
                <h5>(27"x35"x15")</h5>
                <h5>©</h5>
            </div>

            <div class="nav">
                <div class="numbers">
                    <button @click="selectedIndex=1" :class="{ selected: selectedIndex == 1}"><h5>1</h5></button>
                    <button @click="selectedIndex=2" :class="{ selected: selectedIndex == 2}"><h5>2</h5></button>
                    <button @click="selectedIndex=3" :class="{ selected: selectedIndex == 3}"><h5>3</h5></button>
                    <button @click="selectedIndex=4" :class="{ selected: selectedIndex == 4}"><h5>4</h5></button>
                </div>
                <div class="description">
                    <p>Originally inspired by japanese floor tables, the height is meant for comfortable seating on the ground. 
                        The table all together weighs about 90lbs, purposefully, to provide stabilty even on a high pile rug. There
                        is a small secret storage compartment under the tabletop as well.
                    </p>
                </div>
            </div>

        </div> 

    </div>
    
</template>

<style scoped>
    @media only screen and (min-width: 800px) {
        .image-container {
            max-width: 1800px
        }
    }

    @media only screen and (max-width: 800px) {
        .image-spacer {
            max-width: 85%;
        }
    }

    .container {

        display:  flex;
        align-items: center;    
        justify-content: center;
        width: 100%;  
        height: 90%;
        max-width: 1700px;

    }

    .image-spacer {
        display: flex;
        max-height: 100%;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        width: auto;
        max-width: 85%

    }

    .image-container {
        display: flex;
        position: relative;
        align-items: center;
        justify-content: center;
        max-width: 100%;
        max-height: 100%;
        overflow:hidden;

    }



    .selected h5{
        color: var(--num-selected-color);
        font-weight: 700;
        
    }

    .caption h3 {
        margin: 0;
    }

    .caption h5 {
        margin: 2;
    }
    .caption {
        display: flex;
        width: 100%;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: baseline;

    }

    .numbers {
        display: flex;
        width: inherit;
        gap: 1%;

    }

    .description {
        display: flex;
        flex-direction: column;
        font-size: 8pt;
        color: var(--p-color);
        margin-top: 10px;
    }
    .description p {
        margin: 0;
    }

    .numbers button {
        font-weight: 400;
        font-size: 8pt;
        color: var(--p-color);

    }





    .image-container img {
        max-width: 100%; 
        max-height: 100%;
        width: auto;
        height: auto;
        border-radius: 6px;
    }

    .nav {
        display: flex;
        justify-content: space-between;
        align-items: flex-start;
        min-height: 10vh;
        color: var(--num-selected-color);
        margin: 0;
        width: 100%;

    }
    .nav h3 {
        font-weight: 500;
        font-size: 12pt;
    }

    h5 {
        font-weight: 400;
        font-size: 8pt;
        color: var(--p-color);
    }


    button {
        background: none; /* Removes background color */
        border: none; /* Removes border */
        margin: 0; /* Removes margin */
        cursor: pointer; /* Adds pointer cursor */
    }

    .back {
        position: absolute;
        left: 0;
        width: 35%;
        height: 100%;
    }

    .forward {
        position: absolute;

        right: 0;
        width: 65%;
        height: 100%;
    }

</style>