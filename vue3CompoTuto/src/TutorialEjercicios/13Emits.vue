<script setup>
import { ref } from 'vue'
import ChildComp from './ChildComp.vue'

const childMsg = ref('Ningún mensaje del hijo aún')
</script>

<template>
    <ChildComp @response="(msg) => childMsg = msg" />
    <p>{{ childMsg }}</p>
</template>