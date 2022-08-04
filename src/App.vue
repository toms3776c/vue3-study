<script setup>
import AppHeder from './components/AppHeder.vue';
import TodoList from './components/TodoList.vue';
import { ref } from 'vue'

const todos = ref([])
const newTodo = ref('')

const addTodo = () => {
  todos.value.push(newTodo.value)
  newTodo.value = ""
}

const removeTodo = (index) => {
  todos.value.splice(index, 1)
}

</script>

<template>
<AppHeder color="green">My Todo</AppHeder>
<AppHeder color="gray"></AppHeder>
<input type="text" size="30" v-model="newTodo">
<button @click="addTodo()">追加</button>

<TodoList v-bind:todos="todos" @removeTodo="removeTodo"></TodoList>

</template>