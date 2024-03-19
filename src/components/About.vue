<template>
    <div class="container">
        <div class="top-spacer"></div>
        <div class="about-container">
            
        
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
                <p>Lorem  ipsum dolor sit amet, 
                    consectetur adipiscing elit, 
                    sed do eiusmod  tempor incididunt ut 
                    labore et dolore magna aliqua. Augue ut lectus arcu bibendum.
                </p>
            </div>

            <div class="links">
                <a href="" target="_blank">instagram</a>
                <a href="https://github.com/ecolijah" target="_blank">github</a>
                <a href="https://www.linkedin.com/in/elijah-lopez-65b809238/" target="_blank">linkedin</a>
            </div>

        </div>
        <div class="image-container">
            <img src="../assets/aboutme-pic.png" alt="aboutmepic" />
        </div>
        </div>
        <div class="bottom-spacer"></div>
    </div>
    
</template>

<style scoped>



.container {
    /* background-color: aquamarine; */
    display: flex;
    flex-direction: column;
    justify-content: center;
    /* min-height:100vh;
    max-height: 100vh; */
    /* padding: 80px; */
}
.top-spacer {
    display: flex;
    min-height: 15vh;
    max-height: 15vh;
    /* background-color: yellowgreen; */
}
.about-container {
    display: flex;
    min-height: 65vh;
    max-height: 65vh;

}
.bottom-spacer {
    display: flex;
    min-height: 20vh;
    max-height: 20vh;
    /* background-color: blueviolet; */
}
.details {
    display: flex;
    flex-direction: column;
    max-width: 500px;
    min-width: 300px;
    padding-right: 90px;
    /* background-color: brown; */
    justify-content: space-between;
}

.nameplate {
    display: flex;
    flex-direction: row;
    align-items: center;
    /* background-color: aquamarine; */
    max-height: 50px;
    justify-content: space-between;
    /* margin-bottom: -10px; */
}

.titles {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;
    /* padding-bottom: 90px; */
    /* background-color: #79A166; */
    gap: 10%;
}
.titles p {
    /* height: 5px; */
    /* background-color: black; */
    margin-bottom: -20px;
    /* background-color: #79A166; */
}

.links {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 15%;
    /* background-color: aliceblue; */

}
.links a {
    color: #9FCB85;
    font-weight: 500;
    text-decoration: none;
    transition:  color 0.5s ease;
}

.links a:hover {
    color: #79a166;
}

.image-container {
    display: flex;
    max-height: 65vh;
    max-width: 80vw;
    min-height: 400px;
    /* padding-right: 20px; */
    /* background-color: blue; */
    
    justify-content: center;
}

img {
        /* width: 1920px; */
        /* height: 90vh; */
        max-width: 100%; /* Maximum width of the image */
        max-height: 65vh; /* Maximum height of the image */
        object-fit: contain; /*Maintain aspect ratio and fit within the container*/
        border-radius: 6px;
        
}

p {
    color: #9e9e9e;
}

h3 {
    color: #9FCB85;
    font-weight: 500;
    font-size: 16pt;
    display: flex;
    justify-content: center;
    align-items: center;
    /* background-color: aqua; */
    height: 50px;
    padding-top: 20px;
}
h1 {
    font-size: 40pt;
    display: flex;
    justify-content: center;
    align-items: center;
    /* background-color: red; */
    max-height: 50px;
    /* padding-bottom: 20px; */
}
</style>