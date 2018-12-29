<!-- 1.html：结构 -->
<template>
  <!-- 只能有一个根标签 -->
  <div id="app">
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/helloworld">helloworld</router-link></li>
    </ul>
    <router-view></router-view>
  </div>
</template>
<!-- 2.行为：处理逻辑 -->
<script>
// 产生关联的组件
//局部注册组件

// 进行注册
export default {
  name: 'app',
  data(){
    return{
    }
  }
}
</script>
<!-- 3.样式：解决样式 -->
<style>
</style>
