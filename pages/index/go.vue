<template>
	<view>
		123
	    <text @click="goTo">goTo</text>
		 <view @click="on">union</view>
	</view>
</template>

<script>
	export default {
		onLoad: ()=> {
			console.log('onLoad',this);
		},
		onUnload: ()=> {
			console.log('onUnload');
		},	
		destroyed(){
			console.log('destroyed');
		},
		data() {
			return {
				a:2
			}
		},
		activated(){
		console.log('activatedgo')	
		},
		mounted(){	
		uni.request({
			    url: "https://api.seniverse.com/v3/weather/now.json?key=oudikeyru8gzhosh&location=beijing&language=zh-Hans&unit=c",
			    success: (res)=> {
			        console.log('res',res)
			    }
			});
		  console.log(this.$route)	
		  uni.$on('update',(data)=>{
		          console.log('监听:' + data.msg,'this',this);
		      })
		},
		methods: {
			on(){

			},
			goTo(){
		// this.$router.push({
		//  path: "/pages/index/goTo",
		//  params:{a:1}
		// })	
		  uni.navigateTo({
			   url: '/pages/index/goTo?name=1',
			 });

			}
		} 
	}
</script>

<style>

</style>
