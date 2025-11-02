<template>
  <div>
    <!-- <button ref="btn" @click="showDom">点我进入尸魂界</button> -->
    <school-info ref="schoolInfo"/>
    <NinJaInfo contury="木叶" name="宇智波佐助" skill="天照"/>
    <NinJaInfo contury="木叶" name="旗木卡卡西" skill="雷切"/>
  </div>
</template>

<script>

import SchoolInfo from './components/SchoolInfo.vue';
import NinJaInfo from './components/NinJaInfo.vue';
export default {
  name:'App', 
  components:{SchoolInfo,NinJaInfo},
  data(){

  },
  methods:{
   
  },
}
</script>



<style>
</style>

<!-- ref属性
  1.被用来给元素或者子组件注册引用信息(id的替代者)
  2.应用在html标签上获取的是真实dom元素,应用在组件标签上的是组件实例对象(vc)
  3.使用方式参考如上的div中的方式
-->