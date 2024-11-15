<script lang="ts">
import { defineComponent } from 'vue'
import Buttons from './Buttons.vue'
import NavBar from './NavBar.vue'

interface Data {
    nameBtnHeader: String;
    styleBtnHeader: Object
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
                <h1></h1>
                <p></p>

                <Buttons :TextContent="nameBtnHeader" :styleBtn="styleBtnHeader"/>
            </div>

            <div id="container_imagesHeader">
                <img src="" alt="">
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
    border: 2px solid red;
    width: 90%;
    min-height: 70vh;
}

</style>