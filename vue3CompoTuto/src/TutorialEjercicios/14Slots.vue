<script setup>
import { ref } from 'vue'
import ChildComp from './ChildComp.vue'

const msg = ref('desde el padre')
</script>

<template>
    <ChildComp>Mensaje: {{ msg }}</ChildComp>
</template>