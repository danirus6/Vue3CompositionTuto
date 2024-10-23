<!-- ChildComp.vue -->
<script setup>
const props = defineProps({
    msg: String
})
// declara los eventos a emitir
const emit = defineEmits(['response'])

// emit con argumento
emit('response', 'hola desde el hijo')
</script>
<template>
    <slot>Contenido fallback</slot>
</template>