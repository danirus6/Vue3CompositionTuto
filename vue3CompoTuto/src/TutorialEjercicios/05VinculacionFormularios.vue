<script setup>
import { ref } from 'vue'

const text = ref('')
</script>

<template>
    <!-- v-model sincroniza automáticamente el valor de <input> con el estado vinculado -->
    <input v-model="text" placeholder="Escribe aquí" />
    <p>{{ text }}</p>
</template>