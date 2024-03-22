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
                    <p>Originally inspired by japanese floor tables, the height is meant for comfortable seating on the ground. The concrete base 
                        weighs about 60lbs, and the table all together about 90lbs. The reason I wanted it so heavy was so it could easily not wobble even when placed upon a high pile rug.
                    </p>
                    <!-- <p>The top comes off from the base, for an easier time trransporting the heavy table.</p> -->
                    <p>There is a small secret storage comportment under the table top, that is good place to hide something needed infrequently, as the tabletop is heavy.</p>
                </div>
            </div>

        </div> 

    </div>
    
</template>

<style scoped>

    .container {

        display:  flex;
        align-items: center;    
        justify-content: center;
        /* background-color: greenyellow;   */
        width: 100%;  
        height: 90%;

    }

    .image-spacer {
        display: flex;
        max-height: 100%;
        /* background-color: red; */
        align-items: center;
        justify-content: center;
        flex-direction: column;
        /* max-width: 90%; */
        width: auto;
        max-width: 75%

    }

    .image-container {
        display: flex;
        position: relative;
        align-items: center;
        justify-content: center;
        max-width: 100%;
        max-height: 100%;
        overflow:hidden;
        /* background-color: brown; */
        /* max-height: 63vh; */
    }



    .selected h5{
        color: #3a3a3a;
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
        justify-content: space-between;
        align-items: baseline;
        /* background-color: aqua; */
        /* margin-bottom: 50px; */
    }

    .numbers {
        display: flex;
        width: inherit;
        /* background-color: aqua; */
        gap: 1%;
        /* margin-top:  5%; */

    }

    .description {
        display: flex;
        flex-direction: column;
        /* background-color: yellowgreen; */
        font-size: 8pt;
        color: #9e9e9e;
        margin-top: 10px;
    }
    .description p {
        margin: 0;
    }

    .numbers button {
        font-weight: 400;
        font-size: 8pt;
        color: #9E9E9E;
        
        /* color: blue; */
    }





    .image-container img {
        max-width: 100%; /* Ensures the image doesn't exceed the width of its container */
        /* max-height: 65vh; */
        max-height: 100%;
        width: auto;
        height: auto;
        border-radius: 6px;

    }

    .nav {
        display: flex;
        justify-content: space-between;
        align-items: flex-start;
        /* background-color: rgb(255, 231, 178); */
        min-height: 10vh;
        /* max-height: 20vh; */
        color: #3a3a3a;
        margin: 0;
        width: 100%;
        /* gap: 16%; */
        /* margin-top: -10px; */
    }
    .nav h3 {
        font-weight: 500;
        font-size: 12pt;
    }

    h5 {
        font-weight: 400;
        font-size: 8pt;
        color: #9e9e9e;
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
        /* background-color: antiquewhite; */
    }
    .forward {
        position: absolute;

        right: 0;
        width: 65%;
        height: 100%;
        /* background-color: antiquewhite; */
    }

</style>