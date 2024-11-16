<script lang="ts">
import { defineComponent } from 'vue'
import TheHeader from './components/TheHeader.vue'
import TheMain from './components/TheMain.vue'

export default defineComponent({
    name: 'App',
    components: { TheHeader, TheMain }
})
</script>

<template>
  
  <TheHeader />

  <TheMain />

</template>

<style scoped>

</style>
