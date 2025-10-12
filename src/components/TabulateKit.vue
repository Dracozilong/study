<template>
        <ul class="todo-main">
          <item-kit 
          v-for="todoObj in todoList" :key="todoObj.id" :todo="todoObj" :checkTodo="checkTodo" :deleteTodo="deleteTodo"/>
      </ul>
</template>

<script>
import ItemKit from './ItemKit.vue';
export default {
  name:'tabulateKit',
  components:{ItemKit},
  props:['todoList','checkTodo','deleteTodo']
}
</script>

<style scoped>
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>