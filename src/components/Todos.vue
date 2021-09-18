<template>
  <TodoItem
    v-for="todo in todos"
    :key="todo.id"
    :todoProps="todo"
    @item-completed="markComplete"
  />
    <!-- v-bind = : -->
    <!-- v-on = @ -->
    <!-- v-bind:key="todo.id" -->
    <!-- v-bind:todoProps="todo" -->
    <!-- v-on:item-completed="markComplete" -->
</template>

<script>
import { ref } from 'vue'
import TodoItem from './TodoItem'

export default {
  name: 'Todos',
  components: { TodoItem },
  setup() {
    const todos = ref([
      {
        id: 1,
        title: 'Viec 1',
        completed: false
      },
      {
        id: 2,
        title: 'Viec 2',
        completed: false
      },
      {
        id: 3,
        title: 'Viec 3',
        completed: false
      }
    ])

    const markComplete = id => {
      todos.value = todos.value.map(todo => {
        if (todo.id === id) {
          todo.completed = !todo.completed
        }
        return todo
      })
    }

    return {
      todos,
      markComplete
    }
  }
}
</script>

<style></style>
