<template>
  <TodoItem v-for="todo in todoes" v-bind:key="todo.id" v-bind:todoProps="todo" />
</template>

<script>
import { ref } from 'vue'
import TodoItem from './TodoItem'

export default {
  name: 'Todoes',
  components: { TodoItem },
  setup() {
    const todoes = ref([
      {
        id: 1,
        title: 'Viec 1',
        completed: true,
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

    return {
      todoes
    }
  }
}
</script>

<style></style>
