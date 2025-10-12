<template>
  <!-- <div>
    <h1 v-text="msg" ref="title"></h1>
    <button ref="btn" @click="showDom">点我进入尸魂界</button>
    <school-info ref="schoolInfo"/>
    <NinJaInfo contury="木叶" name="宇智波佐助" skill="天照"/>
    <NinJaInfo contury="木叶" name="旗木卡卡西" skill="雷切"/>
  </div> -->

  <div id="root">
  <div class="todo-container">
    <div class="todo-wrap">
      <top-kit :addTodo="addTodo"/>
      <tabulate-kit :todoList="todoList" :checkTodo="checkTodo" :deleteTodo="deleteTodo"/>
      <bottom-kit :todoList="todoList"/>
    </div>
  </div>
</div>
</template>

<script>
import BottomKit from './components/BottomKit.vue';
import TabulateKit from './components/TabulateKit.vue';
import TopKit from './components/TopKit.vue';

// import SchoolInfo from './components/SchoolInfo.vue';
// import NinJaInfo from './components/NinJaInfo.vue';
export default {
  name:'App', 
  components:{TopKit,TabulateKit,BottomKit},
  data(){
    return{
        todoList:[
        {
          id:"001",
          title:"吃饭",
          isCompleted:true
        },
        {
          id:"002",
          title:"抽烟",
          isCompleted:false
        },
        {
          id:"003",
          title:"嫖娼",
          isCompleted:true
        }
      ],
    }
  },
      methods:{
        addTodo(data){
          console.log('zqs',data)
          this.todoList.unshift(data)
        },
        checkTodo(id){
          this.todoList.forEach((todo)=>{
            if(todo.id ===id){
              todo.isCompleted = !todo.isCompleted
              console.log('zhangqs',todo.title,todo.isCompleted)
            }
          })
        },
        deleteTodo(id){
          this.todoList = this.todoList.filter(todo => todo.id !== id)
        }
      }
    }
  // components:{SchoolInfo,NinJaInfo},
  // data(){
  //   return{
  //     msg:'风遁！螺旋手里剑'
  //   }
  // },
  // methods:{
  //   showDom(){
  //     console.log(this.$refs.title) // 真实dom元素
  //     console.log(this.$refs.btn)   // 真实dom元素
  //     console.log(this.$refs.schoolInfo) // school组件的实例对象(VC)
  //   }
  // }

</script>
<style>
/*base*/
body {
  background: #fff;
}

.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn:focus {
  outline: none;
}

.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

/*header*/

/*main*/

/*item*/


/*footer*/


</style>

<!-- ref属性
  1.被用来给元素或者子组件注册引用信息(id的替代者)
  2.应用在html标签上获取的是真实dom元素,应用在组件标签上的是组件实例对象(vc)
  3.使用方式参考如上的div中的方式
-->