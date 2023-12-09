<template>
    <div>
      <ul>
        <li v-for="todo in todos" :key="todo.id">
          <span>{{ todo.text }}</span>
          <button id="edit" @click="editTodo(todo)">Edit</button>
          <button id="edit" @click="deleteTodo(todo.id)">Delete</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      todos: Array,
    },
    methods: {
      deleteTodo(todoId) {
        this.$emit('deleteTodo', todoId);
      },
      editTodo(todo) {
        const updatedText = prompt('Edit Todo:', todo.text);
        if (updatedText !== null) {
          this.$emit('editTodo', { ...todo, text: updatedText });
        }
      },
    },
  };
  </script>
  