<template>
	<view class="container">
		<view class="intro">1本项目已包含uni ui组件，无需import和注册，可直接使用。在代码区键入字母u，即可通过代码助手列出所有可用组件。光标置于组件名称处按F1，即可查看组件文档。</view>
		<text class="intro">详见：</text>
		<uni-link :href="href" :text="href"></uni-link>
	    <view @click="test">go</view>
		 <view @click="test1">goNvue</view>
	   <input v-model="message" placeholder="edit me">
		<text>span</text><text>span</text>
	<!-- 	      <view v-for="(item, bindex) in items" :key='bindex'>
		                {{ bindex }} - {{ item.message }}
		            </view>
	      <view v-for="(value, name, aindex) in object" :key='aindex'>
	                     {{ aindex }}. {{ name }}: {{ value }}
	                </view> -->
		   <picker class='my-picker' @change="bindPickerChange" :value="index" :range="array">
		                <view class="one-picker">
		                    当前选择：{{array[index]}}
		                </view>
		     </picker>		
	<!-- 	<radio-group class="radio-group" @change="radioChange">
				                 <label class="radio" v-for="(item, dindex) in items" :key="item.name">
				                     <radio :value="item.name" :checked="item.checked" /> {{item.value}}
				                 </label>
		 </radio-group> -->
		 
		  <uni-badge text="1"></uni-badge>
		  <Com :age=2  ></Com>
		  <view @click="scan">开启扫码barcode</view>
	</view>
</template>

<script>
	import Com from './com.vue'
	export default {
		components:{Com },
		data() {
			return {
				      items: [{
				                            name: 'USA',
				                            value: '美国'
				                        },
				                        {
				                            name: 'CHN',
				                            value: '中国',
				                            checked: 'true'
				                        },
				                        {
				                            name: 'BRA',
				                            value: '巴西'
				                        },
				                        {
				                            name: 'JPN',
				                            value: '日本'
				                        },
				                        {
				                            name: 'ENG',
				                            value: '英国'
				                        },
				                        {
				                            name: 'TUR',
				                            value: '法国'
				                        }
				                    ],
				index: 0,
				array: ['A', 'B', 'C'],
				message:123,
				href: 'https://uniapp.dcloud.io/component/README?id=uniui',
				items: [
				  { message: 'Foo' },
				  { message: 'Bar' }
				 ],
				   object: {
				                         title: 'How to do lists in Vue',
				                         author: 'Jane Doe',
				                         publishedAt: '2020-04-10'
				                     }
			}
		},
		activated(){
		  console.log('activated')
		},
		mounted(){
		  console.log('mounted')	
		},
		methods: {
			test1(){
				console.log('test1')
				this.$router.push({
				 path: "/pages/index/nvue"
				})
			},
			test(){
				console.log('test')
				
		//在起始页面跳转到test.vue页面并传递参数
		uni.navigateTo({
		    url: '/pages/index/go'
		});
			},
			scan(){
			 console.log('scan')
			 // 允许从相机和相册扫码
			 uni.scanCode({
			     success: function (res) {
			         console.log('条码类型：' + res.scanType);
			         console.log('条码内容：' + res.result);
			     }
			 });
	
			},
			 bindPickerChange(e) {
			      console.log(e)
			}

		}
	}
</script>
<style lang="stylus"  scoped>
>>>.radio-group{
	.uni-radio-input-checked{
		background-color:red
	}   
   }

</style>
<style lang="stylus" >
	

	.container {
		padding: 20px;
		font-size: 14px;
		line-height: 24px;		
	 .intro{
		color:red;
	}
	}

</style>
