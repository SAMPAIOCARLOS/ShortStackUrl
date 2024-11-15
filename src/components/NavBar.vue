<script lang="ts">
import { defineComponent, ref } from 'vue'
import Buttons from './Buttons.vue'
import ListFull from './ListFull.vue'
import LogoMain from './LogoMain.vue'

interface Data {
    listCreateNavBar: String[];
    nameBtnNavBar: String;
    showListFull: Boolean;
    show_shadow: Boolean;
}

export default defineComponent({
    name: 'NavBar',
    components: { Buttons, ListFull, LogoMain },
    data(): Data {
        return {
            listCreateNavBar: ['Features', 'Pricing', 'Resourcer'],
            nameBtnNavBar: 'Sing up',
            showListFull: false,
            show_shadow: false
        }
    },
    methods: {
        toggle_btn(): void {
            const hamburguerRef = this.$refs.hamburguerRef as HTMLElement | null;

            hamburguerRef.classList.toggle('active')

            if(hamburguerRef.classList.contains('active')) {
                this.showListFull = true
                this.show_shadow = true
            } else {
                this.showListFull = false
                this.show_shadow = false
            }
        },
        openListFull(list_full: HTMLElement): void {
            list_full.classList.add('active');
        }

    }
})
</script>

<template>

    <div id="shadow" v-if="show_shadow"></div>

    <nav>
        <div class="container_main_center">
            <div id="container_content_navBar">

                <div id="groupOneNavBar">
                    
                    <LogoMain />

                    <ul id="listNavBar">
                        <li v-for="(itemListNavBar, index) in listCreateNavBar" :key="index">{{ itemListNavBar }}</li>
                    </ul>
                </div>

                <div id="groupTwoNavBar">
                    <p>Login</p>

                    <Buttons :TextContent="nameBtnNavBar"/>
                </div>

                <div class="hamburguer" @click="toggle_btn" ref="hamburguerRef">
                    <span class="line-span"></span>
                    <span class="line-span"></span>
                    <span class="line-span"></span>
                </div>
            </div>

            

            
        </div>
    </nav>

    <ListFull @eventListFull="openListFull" v-if="showListFull"/>
    
</template>

<style scoped>
#shadow {
    width: 100vw;
    height: 100vh;
    background-color: #00000091;
    z-index: 10;
    position: fixed;
}
nav {
    width: 100vw;
    height: 6rem;
    background-color: #ffffff;
    position: fixed;
    transform: translateY(-2px);
    z-index: 50;
}

#container_content_navBar {
    width: 100%;
    height: 6rem;
    /* border: 2px solid blue; */
    display: flex;
    justify-content: space-between;
    align-items: center;
}

#groupOneNavBar {
    width: 40%;
    display: flex;
    /* border: 1px solid red; */
    gap: 40px;
    align-items: center;
}

#listNavBar {
    display: flex;
    gap: 20px;
    list-style: none;
    font-weight: bold;
}
#listNavBar > li {
    opacity: 0.6;
    cursor: pointer;
    transition: all 0.5s;
}
#listNavBar > li:hover {
    opacity: 1;
}
#groupTwoNavBar {
    width: 15%;
    /* border: 2px solid blue; */
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}
#groupTwoNavBar > p {
    font-weight: bold;
    opacity: 0.6;
    transition: all 0.5;
    cursor: pointer;
}
#groupTwoNavBar > p:hover {
    opacity: 1;
}

.hamburguer {
    display: none;
    flex-direction: column;
    gap: 5px;
    z-index: 1000;
}



/* .hamburguer.active {
    position: fixed;
    top: 3%;
    left: 90%;

    descomentar caso precise mover o botão de lugar apos add de class
} */

.line-span {
    width: 30px;
    height: 3px;
    border-radius: 10px;
    background-color: #000000;
    transition: 0.5s;
}

.hamburguer.active .line-span:nth-child(2) {
    opacity: 0;
    transition: 0.3s;
}
.hamburguer.active .line-span:nth-child(1) {
    transform: translateY(8px) rotate(45deg);
    transition: 0.5s;
    /* background-color: #000000; */
}
.hamburguer.active .line-span:nth-child(3) {
    transform: translateY(-8px) rotate(-45deg);
    transition: 0.5s;
    /* background-color: #000000; */
}


.line-span:nth-child(1) {
    background-color: #000000;
}
.line-span:nth-child(2) {
    background-color: #000000;
}
.line-span:nth-child(3) {
    background-color: #000000;
}


@media(max-width: 1000px) {
    .hamburguer {
        display: flex;
    }
    #groupTwoNavBar {
        display: none;
    }
    #listNavBar {
        display: none;
    }
}
@media(min-width: 1000px) {
    #shadow {
        display: none;
    }
}

/* @media(max-width: 700px) {
    
} */
</style>
