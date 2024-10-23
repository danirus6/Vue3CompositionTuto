<script setup>
import { ref } from 'vue'
let i = 0;
const parentMessage = ref('Parent')
const items = ref([{ message: 'Foo' }, { message: 'Bar' }, { message: 'pepe' }])
const testeo = ref([{ title: i + 1, message: "mensaje" }, { title: i + 2, message: "mensaje2" }])
const increment = () => {
    i++;
    testeo.value.push({ title: i, message: "mensajetest" })

}
</script>

<template>
    <li v-for="(item, index) in items">
        {{ parentMessage }} - {{ index }} - {{ item.message }}
    </li>
    <li v-for="(test, i) in testeo">
        {{ parentMessage }} - {{ i }} - {{ test.title }} - {{ test.message }}
    </li>
    <button @click="increment">
        incrementando objetos
    </button>
</template>