<template>
          <div class="todo-footer" v-show="total">
        <label>
          <input type="checkbox" v-model="isAll"/>
        </label>
        <span>
          <span>已完成{{computeTotal}}</span> / 全部{{total}}
        </span>
        <button class="btn btn-danger">清除已完成任务 </button>
      </div>
</template>

<script>
export default {
  name:"bottomKit",
  props:['todoList','checkAllTodo'],
  computed:{
    total(){
      return this.todoList.length
    },
    computeTotal(){
      console.log('####',this.todoList)
      return this.todoList.reduce((pre,todo)=>pre + (todo.isCompleted?1:0),0)
    },
    isAll:{
      get(){
        return this.computeTotal  === this.total && this.total > 0
      },
      set(value){
        console.log('%%%',value)
         this.checkAllTodo(value)
      }
    }
  }
}
</script>

<style scoped>
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>