<template>
  <footer>
  	<p>{{copyright}} {{title}}</p>
  </footer>
</template>

<script>
export default {
  name: 'app-footer',
  props:{
    title:{
      typle:String
    }
  },
  data () {
    return {
    	copyright:"Copyright 2007 Vue Demo"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
footer{
	background: #222;
	padding:6px;

}
p{
	color:lightgreen;
	text-align: center;
}
</style>
