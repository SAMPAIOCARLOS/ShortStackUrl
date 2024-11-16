<script lang="ts">
import { defineComponent } from 'vue'
import Buttons from './Buttons.vue'

interface Data {
    nameBtnInputMain: String;
    styleBtnInputMain: Object;
}

export default defineComponent({
    name: 'TheMain',
    components: { Buttons },
    data(): Data {
        return {
            nameBtnInputMain: 'shorten it',
            styleBtnInputMain: {
                borderRadius: '7px',
                width: '150px',
                height: '40%',
                fontSize: '1.2rem'
            }
        }
    },
    methods: {
        handleSubmit(event): void {
            event.preventDefault()
            
        }
    }
})
</script>

<template>
    <main>
        <div class="container_main_center">
            <section id="section_inputUrl">
                <form @submit="handleSubmit">
                    <input type="text" placeholder="Enter the url here">
                    <Buttons :TextContent="nameBtnInputMain" :styleBtn="styleBtnInputMain"/>
                    <!-- <span :style="teste" id="alertInput">teste</span> FALTA ARRUMAR O FORM PARA O SPAN FICAR NO LUGAR CERTO -->
                </form>
                <div id="container_linkShort">
                </div>
            </section>

            
            <section>
            </section>
        </div>
    </main>
</template>

<style scoped>
main {
    width: 100vw;
    min-height: 100vh;
    background-color: aliceblue;
}

#section_inputUrl {
    /* border: 2px solid red; */
    width: 100%;
    min-height: 20vh;
    transform: translateY(-50%);
}
form {
    width: 100%;
    height: 20vh;
    background: url('../assets/images/bg-shorten-desktop.svg') #352b52;
    background-position: center;
    background-repeat: no-repeat;
    background-size: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
    border-radius: 10px;
}
input {
    width: 70%;
    height: 40%;
    padding: 15px;
    border-radius: 7px;
    border: 3px solid transparent;
    transition: all 0.5s;
    font-size: 2rem;
}
/* input::placeholder {
    font-size: 2rem;
    transform: translateY(7px);
} */
input:hover {
    border: 3px solid  rgb(97, 229, 255);

}
</style>