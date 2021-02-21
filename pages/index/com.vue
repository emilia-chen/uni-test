<template>
	<view>
		 <!-- 我是子组件componentA -->
		            <view>{{age}}</view>
	</view>
</template>

<script>
    export default {
            props: {
                // 检测类型 + 其他验证
                age: {
                    type: Number,
                    default: 0,
                    required: true,
                    validator: function(value) {
                        return value >= 0
                    }
                }
            }
        }
</script>

<style>

</style>
