<template>
  <p :class="['todo-item', todoProps.completed ? 'is-completed' : '']">
    <input
      type="checkbox"
      :checked="todoProps.completed"
      @change="markItemCompleted" 
    />
    {{ todoProps.title }}
    <button class="del-btn" @click="deleteItem">
      Delete
    </button>
  </p>
</template>

<script>

export default {
  name: 'TodoItem',
  props: ['todoProps'],

  setup(props, context) {
    const markItemCompleted = () => {
      // console.log(props)
      context.emit('item-completed', props.todoProps.id)
    }

    const deleteItem = () => {
      context.emit('delete-item', props.todoProps.id)
    }
    return {
      markItemCompleted,
      deleteItem
    }
  }
}

</script>

<style>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  margin: 0;
  border-bottom: 1px #ccc dashed;
}

.is-completed {
  text-decoration: line-through;
}

.del-btn {
  background: #ff0000;
  color: #fff;
  border: none;
  cursor: pointer;
  float: right;
}
</style>
