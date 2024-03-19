<template>
    <div class="container">
        <div class="details">

            <div class="heading">
                <div class="nameplate">
                    <h1>elijah lopez</h1>
                    <h3>houston, tx</h3>
                </div>
              
                <div class="titles">
                    <p>software developer</p>
                    <p>designer / craftsman</p>
                </div>

            </div>

            <div class="about-text">
                <p>Lorem  ipsum dolor sit amet, 
                    consectetur adipiscing elit, 
                    sed do eiusmod  tempor incididunt ut 
                    labore et dolore magna aliqua. Amet consectetur  
                    adipiscing elit pellentesque habitant. Magna etiam
                    tempor orci eu  lobortis. Augue ut lectus arcu bibendum.
                </p>
            </div>

            <div class="links">
                <p>instagram</p>
                <p>github</p>
                <p>linkedin</p>
            </div>

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
    justify-content: center;
    /* padding: 80px; */
}
.details {
    display: flex;
    flex-direction: column;
    max-width: 500px;
    min-width: 300px;
    background-color: brown;
    justify-content: space-between;
}

.nameplate {
    display: flex;
    flex-direction: row;
    align-items: baseline;
    background-color: aquamarine;
    max-height: 80px;
    justify-content: space-between;
}

.titles {

}

.links {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding-right: 20px;
}

.image-container {
    display: flex;
    max-height: 570px;
    max-width: 430px;
    background-color: blue;
    justify-content: center;
}

img {
        /* width: 1920px; */
        /* height: 90vh; */
        max-width: 100%; /* Maximum width of the image */
        max-height: 100%; /* Maximum height of the image */
        object-fit: contain; /*Maintain aspect ratio and fit within the container*/

    }
</style>