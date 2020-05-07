<template>
	<div>
		<HelloWorld msg="Welcome to Your Vue.js App"/>
		<button id="btn" @click="name">提交</button>
		<div id="anketo">{{project}}</div>
	</div>
</template>

<script>
	import HelloWorld from '@/components/HelloWorld.vue'
	export default {
		data(){
			return{
				project:{},
				anketoList:[]
			}
		},
		name: 'Info',
		components: {
			HelloWorld
		},
		methods: {
			name:function() {
				this.$axios.get('http://127.0.0.1:8080/whole/getbyid/1').then((res)=>{
					this.project = res.data.Project
					console.log('res:',res.data.Project)
				}).catch(err =>{
					console.log(err)
				}).finally(() =>{
					
				})
			}
		}
	}
</script>

<style>
</style>
