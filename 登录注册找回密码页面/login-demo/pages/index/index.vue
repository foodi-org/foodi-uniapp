<template>
	<view class="content">
		<view>
			<u-button type="primary" shape="circle" @click="toUrl('/pages/login/login')">本机号码一键登录</u-button>
		</view>
		<view>
			<u-button type="success" shape="circle" @click="toUrl('/pages/login/login-pwd')">密码登录</u-button>
		</view>
		<view>
			<u-button type="success" shape="circle" @click="toUrl('/pages/login/login-code')">验证码登录</u-button>
		</view>
		<view>
			<u-button type="error" shape="circle" @click="toUrl('/pages/login/resst-pwd')">重置密码</u-button>
		</view>
		<view>
			<u-button type="error" shape="circle" @click="toUrl('/pages/login/retrieve-pwd')">忘记密码</u-button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad() {
			
		},
		methods: {
			toUrl(url) {
				uni.navigateTo({
					url: url
				})
			}
		}
	}
</script>

<style scoped lang="scss">
	.content {
		padding: 30rpx;
		
		view {
			margin: 30rpx 0;
		}
	}
</style>
