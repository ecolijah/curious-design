<template>
    <div class="container">
        <!-- <div class="top-spacer"></div> -->
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
                <p><strong>Hi!</strong> ive always enjoyed the process of making. Either physical or digital, doesnt matter, 
                    the process is the same, and the result is usually trivial. (like a youth sports trophy) 
                    Slowly accumulating progress and knowledge through probing different approaches and techniques.
                    A never ending aspiration to be be more adept to solve a problem than you were just one project ago.
                </p>
                <p>Ah, thats what it's all about.
                </p>
            </div>

            <div class="links">
                <!-- <a href="" target="_blank">instagram</a> -->
                <a href="https://github.com/ecolijah" target="_blank">github</a>
                <a href="https://www.linkedin.com/in/elijah-lopez-65b809238/" target="_blank">linkedin</a>
            </div>

            </div>
            <div class="image-container">
                <img src="../assets/aboutme-pic.png" alt="aboutmepic" />
            </div>
        </div>
        <!-- <div class="bottom-spacer"></div> -->
    </div>
    
</template>

<style scoped>

@media only screen and (min-width: 801px) {
        .image-container {
        display: flex;
        max-height: 50vh;
        width: 30vw;
        justify-content: center;
    }
}

@media only screen and (max-width: 800px) {
    .image-container {
    display: flex;
    max-height: 40vh;
    justify-content: center;
}
}
.heading {
    display:  flex;
    flex-direction: column;
}
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;

    padding: 20px;
}
.top-spacer {
    display: flex;
    min-height: 20vh;
    max-height: 20vh;
}

.about-container {
    display: flex;
    flex-wrap: wrap-reverse;
    max-height: 100vh;

    justify-content: center;

}
.bottom-spacer {
    display: flex;
    min-height: 25vh;
    max-height: 25vh;
}
.details {
    display: flex;
    flex-direction: column;
    max-width: 500px;
    max-height: 60vh;;

    justify-content: space-between;
}

.nameplate {
    display: flex;
    flex-direction: row;
    align-items: baseline;
    flex-wrap: wrap;
    justify-content: space-between;
}

.titles {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;

    gap: 10%;
}
.titles p {

    margin: 0;
    color: var(--num-selected-color-2);
}

.links {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    gap: 30%;

}
.links a {
    color: var(--accent-color);
    font-weight: 500;
    text-decoration: none;
    transition:  color 0.5s ease;
    font-size: 12pt;
}

.links a:hover {
    color: var(--accent-color-hover);

}



img {

        display: flex;
        max-width: 100%; 
        max-height: 100%;
        object-fit: contain; 
        border-radius: 6px;
        -webkit-box-shadow: 5px 5px 7px 0px var(--box-shadow-color); 
        box-shadow: 5px 5px 7px 0px var(--box-shadow-color);
        
}

p {
    color: var(--p-color);
    font-weight: 400;
    font-size: 10pt;
}

h3 {
    color: var(--accent-color);
    font-weight: 500;
    font-size: 16pt;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0;
}
h1 {
    font-size: 40pt;
    display: flex;
    justify-content: center;
    align-items: center;
    max-height: 60px;
    margin: 0;
}
</style>