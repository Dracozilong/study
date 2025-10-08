<template>
   <div>
     <h2 @click="showName">番队:{{team}}</h2>
     <h2>队长:{{captain}}</h2>
   </div>
</template>

<script>
import { tip } from '@/mixin';

export default {
   name:'SchoolInfo',
   data(){
    return {
     team:'六番队',
     captain:'朽木白哉'
    }
   },
   mixins:[tip]
}
</script>

<style>

</style>

<!-- mixin(混入)
 功能:可以把多个组件共用的配置提取成一个混入的对象
 使用方式:
    第一步定义混合,详见mixin.js
    第二步使用混入,例如
      (1):全局混入:Vue.mixin(xxx)
      (2):局部混入:mixins:['xxx'] -->