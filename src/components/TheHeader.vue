<script lang="ts">
import { defineComponent } from 'vue'
import Buttons from './Buttons.vue'
import NavBar from './NavBar.vue'

interface Data {
    nameBtnHeader: String;
    styleBtnHeader: Object;
}

export default defineComponent({
    name: 'teste',
    components: { NavBar, Buttons },
    data(): Data {
        return {
            nameBtnHeader: 'Get Started',
            styleBtnHeader: {
                width: '180px',
                fontSize: '20px'
            }
        }
    }
})
</script>

<template>
    <NavBar />
    <header>
        
        <div id="containerContentHeader">
            <div id="textContentHeader">
                <h1>More than just shorter links</h1>
                <p>Build your brand's recognition and get detailed insights on how your links are performing.</p>

                <Buttons :TextContent="nameBtnHeader" :styleBtn="styleBtnHeader"/>
            </div>

            <div id="container_imagesHeader">
                <img src="../assets/images/illustration-working.svg" alt="">
            </div>
        </div>

    </header>
</template>

<style scoped>

header {
    width: 100vw;
    min-height: 100vh;
    /* border: 3px solid red; */
    padding-top: 6rem;
    display: flex;
    justify-content: flex-end;
    align-items: center;
}
#containerContentHeader {
    /* border: 2px solid red; */
    width: 90%;
    min-height: 70vh;
    display: flex;
    justify-content: space-between;
    gap: 20px;
}
#textContentHeader {
    /* border: 2px solid blue; */
    width: 55%;
    min-height: 70vh;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
}

h1 {
    color: #34313D;
    font-size: 6vw;
}
p {
    font-size: 2vw;
    color: #34313D;
    width: 90%;
}

#container_imagesHeader {
    /* border: 3px solid green; */
    width: 40%;
    min-height: 70vh;
}
#container_imagesHeader > img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}

@media(max-width: 1000px) {
    h1 {
        color: #34313D;
        font-size: 7vw;
    }
    p {
        font-size: 2.5vw;
        color: #34313D;
        width: 90%;
    }
}
@media(max-width: 900px) {
    #containerContentHeader {
        flex-wrap: wrap-reverse;
        width: 100%;
    }
    #container_imagesHeader {
        width: 100%;
        padding: 50px 0;
        display: flex;
        justify-content: center;
    }
    #container_imagesHeader > img {
        width: 80%;
        height: 100%;
        object-fit: contain;
    }

    #textContentHeader {
        width: 100%;
        padding: 0 10%;
    }
}

@media(max-width: 650px) {
    #container_imagesHeader {
        min-height: 50vh;
    }

    h1 {
        font-size: 10vw;
    }
    p {
        font-size: 3.5vw;
    }
}

@media(max-width: 600px) {
    #container_imagesHeader > img {
        width: 100%;
        /* transform: translateX(-30px); */
    }
    #textContentHeader {
        min-height: 40vh;
        gap: 40px;
    }
}

@media(max-width: 400px) {
    h1 {
        font-size: 11vw;
    }
    p {
        font-size: 3.5vw;
        width: 100%;
    }
}
@media(max-width: 350px) {
    #container_imagesHeader {
        min-height: 30vh;
    }
     p {
        font-size: 4.5vw;
    }
}
</style>