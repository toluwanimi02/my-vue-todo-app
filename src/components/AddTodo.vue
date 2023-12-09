
<template>
    <div>
      <input v-model="newTodo" placeholder="Enter todo here" />
      <button @click="addNewTodo">Add Todo</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTodo: '',
      };
    },
    methods: {
      addNewTodo() {
        if (this.newTodo.trim() !== '') {
          this.$emit('addTodo', this.newTodo);
          this.newTodo = '';
        }
      },
    },
  };
  </script>
  