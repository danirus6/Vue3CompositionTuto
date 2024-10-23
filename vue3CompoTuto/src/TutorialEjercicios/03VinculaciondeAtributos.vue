<!-- Vinculacion de atributos -->
<script setup>
import { ref } from 'vue'

const titleClass = ref('title')
</script>

<template>
    <!-- añade aquí la vinculación a la clase dinámica -->
    <h1 :class="titleClass">Hazme rojo</h1>

</template>

<style>
.title {
    color: red;
}
</style>