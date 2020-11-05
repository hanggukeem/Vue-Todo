<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{todo.title}}</p>
      <button @click="$emit('del-todo', todo.id)" 
      class="del">X</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete(){
      this.todo.completed = !this.todo.completed;
  }
  }
}
</script>
<style scoped>
div {
  position: relative;
}
  .todo-item {
    background: #f4f4f4;
    padding: 10px;
    border: 1px solid #ccc;
  }

  .is-complete {
    text-decoration: line-through;
  }

  .del {
    background: #ff0000;
    color: #ffffff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
  position: absolute;
  right: 0;
  top: 20px;    
  }
</style>