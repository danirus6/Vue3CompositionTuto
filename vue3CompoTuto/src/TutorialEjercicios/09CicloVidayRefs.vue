<script setup>
import { ref, onMounted } from 'vue'

const pElementRef = ref(null)

onMounted(() => {
    console.log("componente montado")
    pElementRef.value.textContent = "pera"; // PARA PODER ACCEDER AL ELEMENTO UNA VEZ CARGADO EL DOM
})
</script>

<template>
    <p ref="pElementRef">hola</p>
</template>