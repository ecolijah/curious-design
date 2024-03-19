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
    <div class="info" :class="{ active: isX}">
        <h3>+1 832 425 6030</h3>
        <h3>elijahlopez0030@gmail.com</h3>
        <button @click="changecolor">click to chnage color</button>

    </div>
    
</template>

<style scoped>
    .info {
        color:blue;
    }
    .active {
        color: red;
    }
</style>