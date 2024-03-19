<script setup>
    import {ref} from "vue";

    var isX =  ref(false);
    function changecolor() {
        isX.value = !isX.value;
        console.log("isX:" + isX.value)
    }



</script>

<!-- <div :class="{ active: isActive }"></div> -->

<template>
    <div class="container">
        <div class="top-spacer"></div>
        <div class="info" :class="{ active: isX}">
        <h3>+1 832 425 6030</h3>
        <h3>elijahlopez0030@gmail.com</h3>
        <!-- <button @click="changecolor">click to chnage color</button> -->

        </div>
    </div>
    
    
</template>

<style scoped>
    .container {
        display: flex;
        flex-direction: column;
    }
    .top-spacer {
        display: flex;
        min-height: 15vh;
        /* background-color: antiquewhite; */
    }
    .info {
        font-size: 10pt;
        display: flex;
        height: 85vh;
        width: 100vw;
        /* background-color: yellowgreen; */
        flex-direction: column;
        justify-content: flex-start;
        align-items: flex-start;
    }

    .info h3 {
        display: flex;
        padding-left: 50px;
        height:fit-content;
        width: fit-content;
        font-weight: 400;
        margin-bottom: -10px;
        color: #9E9E9E;

        /* background-color: blueviolet; */
        
        
    }
    .active {
        color: red;
    }
</style>