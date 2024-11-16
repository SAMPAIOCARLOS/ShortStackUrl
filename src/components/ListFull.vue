<script lang="ts">
import { defineComponent } from 'vue'
import LogoMain from './LogoMain.vue'

export default defineComponent({
    name: 'ListFull',
    components: { LogoMain },
    mounted() {
        const list_full = this.$refs.listFull as HTMLElement | null;
        
        if(list_full) {
            this.$emit('eventListFull', list_full)
        }
        
    }
})
</script>

<template>
    <div id="list_full" ref="listFull">
        
        <div id="containerLogoListFull">
            <LogoMain />
        </div>
    </div>
</template>

<style scoped>
#list_full {
    width: 40%;
    height: 100%;
    position: fixed;
    left: 10%;
    top: 0%;
    background-color: #ffffff;
    z-index: 300;
    transition: 0.2s;
    display: flex;
    flex-direction: column;
    /* justify-content: space-around; */
    align-items: center;
    border-top-right-radius: 5vw;
    border-bottom-right-radius: 5vw;
    overflow: auto;
    gap: 50px;
    padding: 0 0 70px 0;
}

#list_full.active {
    left: 0%;
}

#containerLogoListFull {
    width: 100%;
    /* border: 2px solid blue; */
    padding: 30px;
}

@media(min-width: 1000px) {
    #list_full {
        display: none;
    }
    
}

@media(max-width: 600px) {
    #list_full {
        width: 70%;
    }
}
/* @media(max-width: 320px) {
    #list_full {
        width: 100%;
    }
} */
</style>