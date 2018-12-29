<!-- 1.html：结构 -->
<template>
  <!-- 只能有一个根标签 -->
  <div id="home">
    <!-- 组件调用 -->
    <!-- 子向父传值  添加事件事件名要跟子组件注册的名字要一样   -->
    <app-header v-on:titleChanged="updateTitle($event)" v-bind:title="title"></app-header>
    <users v-bind:users="users"></users>
    <users v-bind:users="users"></users>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>
<!-- 2.行为：处理逻辑 -->
<script>
// 产生关联的组件
//局部注册组件
import Users from './Users'
import Header from './Header'
import Footer from './Footer'
// 进行注册
export default {
  name: 'home',
  data(){
    return{
      
      users:[
      
      ],
      title:"传递的是一个值（string number boolean）",
    }
  },
  methods:{
     updateTitle(title){
      this.title=title
    }
  },
  created(){
    this.$http.get("http://jsonplaceholder.typicode.com/users")
    .then((data) => {
      //console.log(data)
      this.users = data.body;
    })
  },
  // beforeCreate(){
  //   alert("beforeCreate组件实例化之前执行的函数，例如：实现加载动画")
  // },
  // created(){
  //   alert("created组件实例化完毕，但页面还未显示，例如：获取网络接口数据，并结束加载动画")
  // },
  // beforeMount(){
  //   alert("beforeMount组件挂在前，页面还未显示，但虚拟DOM已经配置")
  // },
  // Mounted(){
  //   alert("Mounted组件挂在后，此方法执行后台，页面显示")
  // },
  // beforeUpdate(){
  //   alert("beforeUpdate组件更新前，页面仍未更新，但虚拟DOM已经配置")
  // },
  // Updated(){
  //   alert("Updated组件更新前，此方法执行后台，页面显示")
  // },
  // beforeDestroy(){
  //   alert("beforeDestroy组件销毁前")
  // },
  // Destroyed(){
  //   alert("Destroyed组件已销毁")
  // },
  components:{
    "users":Users,
    "app-header":Header,
    "app-footer":Footer
  }
}
</script>
<!-- 3.样式：解决样式 -->
<style>
</style>
