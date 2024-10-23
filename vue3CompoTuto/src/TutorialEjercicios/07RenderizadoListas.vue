<script setup>
import { ref } from 'vue'

// dar a cada tarea (todo) un id único
let id = 0

const newTodo = ref('')
const todos = ref([
  { id: id++, text: 'Aprender HTML' },
  { id: id++, text: 'Aprender JavaScript' },
  { id: id++, text: 'Aprender Vue' }
])

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value })
  newTodo.value = ''
}

function removeTodo(todo) {
  todos.value = todos.value.filter((selected) => selected !== todo)
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Añadir Tarea</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>

<!-- 
<script setup>
import { ref } from 'vue'
let i = 0;
const parentMessage = ref('Parent')
const items = ref([{ message: 'Foo' }, { message: 'Bar' }, {message:'pepe'}])
const testeo = ref([{title:'t1',message:"mensaje"},{title:'t2',message:"mensaje2"}])
const increment = () => {
i++;
testeo.value.push({title: i, message:"mensajetest"})

}
</script>

<template>
  <li v-for="(item, index) in items">
    {{ parentMessage }} - {{ index }} - {{ item.message }}
  </li>
  <li v-for="(test, i) in testeo" @click="increment">
    {{ parentMessage }} - {{ i }} - {{ test.title }} - {{ test.message }}
  </li>
</template> -->