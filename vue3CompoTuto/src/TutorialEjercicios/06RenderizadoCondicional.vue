<script setup>
import { ref } from 'vue'

const awesome = ref(true)

const toggle = () => {
    awesome.value = !awesome.value
}
</script>

<template>
    <button @click="toggle">alternar</button>
    <h1 v-if="awesome">¡Vue es increíble!</h1>
    <h1 v-else>Oh no 😢</h1>
</template>