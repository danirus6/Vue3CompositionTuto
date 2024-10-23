<script setup>
import { ref } from 'vue'

const count = ref(0)
const increment = () => {
    count.value++;
}
</script>

<template>
    <!-- haz que este botón funcione -->
    <button @click="increment">El contador está en: {{ count }}</button>
</template>