<script setup>
import { ref, computed } from 'vue'

let id = 0

const newTodo = ref('')
const hideCompleted = ref(false)
const todos = ref([
    { id: id++, text: 'Aprender HTML', done: true },
    { id: id++, text: 'Aprender JavaScript', done: true },
    { id: id++, text: 'Aprender Vue', done: false }
])
// Te presentamos a computed(). Podemos crear una ref computada que calcule su .value en base a otras fuentes de datos reactivas
const filteredTodos = computed(() => {
    // retorna las tareas filtradas basándose en
    // `todos.value` y `hideCompleted.value`

    // Una propiedad computada rastrea otros estados reactivos utilizados en su cómputo como dependencias.Almacena el resultado en caché y lo actualiza automáticamente cuando sus dependencias cambian.
    return hideCompleted.value
        ? todos.value.filter((selected) => !selected.done)
        : todos.value
})

function addTodo() {
    todos.value.push({ id: id++, text: newTodo.value, done: false })
    newTodo.value = ''
}

function removeTodo(todo) {
    todos.value = todos.value.filter((t) => t !== todo)
}
</script>

<template>
    <form @submit.prevent="addTodo">
        <input v-model="newTodo" />
        <button>Añadir Tarea</button>
    </form>
    <ul>
        <li v-for="todo in filteredTodos" :key="todo.id">
            <input type="checkbox" v-model="todo.done" />
            <span :class="{ done: todo.done }">{{ todo.text }}</span>
            <button @click="removeTodo(todo)">X</button>
        </li>
    </ul>
    <button @click="hideCompleted = !hideCompleted">
        {{ hideCompleted ? 'Mostrar todo' : 'Ocultar completada' }}
    </button>
</template>

<style>
.done {
    text-decoration: line-through;
}
</style>