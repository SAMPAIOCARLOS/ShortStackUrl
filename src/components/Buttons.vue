<script lang="ts">
import { defineComponent, PropType } from 'vue'

export default defineComponent({
    name: 'Buttons',
    props: {
        TextContent: { type: String as PropType<String>, required: true },
        styleBtn: { type: Object as PropType<Object>, default: () => ({}), }
    }
})
</script>

<template>
    <button :style="styleBtn">
        {{ TextContent }}
    </button>
</template>

<style scoped>
button {
    width: 100px;
    padding: 10px 20px;
    background-color: rgb(97, 229, 255);
    color: #ffffff;
    font-weight: bold;
    border-radius: 100px;
    border: none;
    outline: none;
    cursor: pointer;
    transition: all 0.4s;
}
button:hover {
    scale: 1.1;
}
</style>
