<script setup>

</script>


<template>
    <div class="container">
        <div class="top-spacer"></div>
        <div class="info" :class="{ active: isX}">
        <h3>+1 832 425 6030</h3>
        <h3>elijahlopez0030@gmail.com</h3>

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
    }
    .info {
        font-size: 10pt;
        display: flex;
        height: 85vh;
        width: 100vw;
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
        color: var(--p-color);

    }

</style>