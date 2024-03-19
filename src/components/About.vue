<template>
    <div class="container">
        <div class="details">
            <h1>about </h1>

        </div>
        <div class="image-container">
            <img src="../assets/aboutme-pic.png" alt="aboutmepic" />
        </div>
    </div>
    
</template>

<style scoped>

.container {
    background-color: aquamarine;
    display: flex;
    flex-direction: row;
}
.details {
    width: 500px;
    background-color: brown;
}

.image-container {
    height: 80vh;
    background-color: aquamarine;
}

img {
        /* width: 1920px; */
        /* height: 90vh; */
        max-width: 100%; /* Maximum width of the image */
        max-height: 100%; /* Maximum height of the image */
        object-fit: contain; /*Maintain aspect ratio and fit within the container*/

    }
</style>