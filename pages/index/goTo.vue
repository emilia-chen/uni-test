<template>
	<view>
		dadasd
	<view @click="emit">uniemit</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		mounted(){
		  console.log(this.$route)	
		},
		activated(){
		console.log('activatedgto')	
		},
		methods: {
			emit(){
				 uni.$emit('update',{msg:'页面更新'})
			}
		}
	}
</script>

<style>

</style>
