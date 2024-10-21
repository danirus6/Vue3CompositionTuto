<script setup>
import { ref,reactive } from 'vue'

// lógica del componente
// declara algún estado reactivo aquí.
  const titleRef = ref('dinamico')
  const title = reactive ({
    title: "Hazme dinamico"
  })
</script>

<template>
  <h1>{{title.title}}</h1>
  <h2>
    {{titleRef}}
  </h2>
</template>