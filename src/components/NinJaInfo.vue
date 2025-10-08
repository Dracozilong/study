<template>
   <div>
     <h1>{{msg}}</h1>
     <h2>村子:{{contury}}</h2>
     <h2>姓名:{{name}}</h2>
     <h3>忍术:{{skill}}</h3>
     <h4>年龄:{{age}}</h4>
   </div>
</template>

<script>
export default {
   name:'NinjaInfo',
   data(){
    return{
    msg:'中忍考试'
    }
   },
   // 简单声明接收
   // props:['contury','name','skill'] 

   // 接收的同时对数据类型进行类型限制
   // props:{
   //    contury:String,
   //    name:String,
   //    skill:String,
   //    age:Number
   // }

   // 接收数据的同时 对数据类型进行限制 + 默认类型的指定 + 必要性的限制
   props:{
      contury:{
         type:String,
         required:true
      },
      name:{
         type:String,
         required:true
      },
      skill:{
         type:String,
         required:true
      },
      age:{
         type:Number,
         default:99
      }
   }
}
</script>

<style>

</style>

<!-- 2025-10-2 066_props 配置 -->
 
<!-- 配置项 props
  功能：让组件接收外部传过来的数据
  具体方式见如上
  备注: props是只读的,Vue底层会监测你对props的修改,如果进行了修改，就会发出警告,
  若业务需求确实需要修改，那么请复制props的内容到data中,然后去data中修改数据 -->