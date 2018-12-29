<template>
  <header v-on:click="changeHeader">
  	<h1>{{title1}} {{title}}</h1>
  </header>
</template>

<script>
export default {
  name: 'app-header',
  //属性传值用prop传入
  props:{
    title:{
      typle:String
    }
  },
  data () {
    return {
    	title1:"Vue.js Demo"
    }
  },
  methods:{
    changeHeader:function(){
      //this.title = "changed"
      //注册事件$emit 参数1：方法名  参数2：传参
      this.$emit("titleChanged","子向父传值")
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header{
	background: lightgreen;
	padding:10px;

}
h1{
	color:#222;
	text-align: center;
}
</style>
