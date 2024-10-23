<!-- ChildComp.vue -->
<script setup>
const props = defineProps({
    msg: String
})
</script>
<script setup>
import { ref } from 'vue'
import ChildComp from './ChildComp.vue'

const greeting = ref('Hola desde el padre')
</script>

<template>
    <ChildComp :msg="greeting" />
</template>