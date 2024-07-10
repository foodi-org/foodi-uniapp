<template>
	<view class="content">
		<view class="title">账号密码登录</view>
		<view class="form">
			<view class="form-item">
				<u-input v-model="form.phone" type="number" placeholder="请输入手机号"/>
			</view>
			<view class="form-item">
				<u-input v-model="form.pwd" type="password" placeholder="请输入登录密码"/>
			</view>
		</view>
		<view class="btn-box">
			<view class="btn u-flex u-row-center u-col-center">
				<text>登录</text>
			</view>
		</view>
		<view class="other">
			<text @click="toUrl('/pages/login/login-code')">验证码登录</text>
			<text @click="toUrl('/pages/login/retrieve-pwd')">忘记密码？</text>
		</view>
		
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				form: {
					phone: '',
					pwd: ''
				}
			}
		},
		methods: {
			toUrl(url) {
				uni.redirectTo({
					url: url
				})
			}
		}
	}
</script>

<style scoped lang="scss">
	.content {
		width: 100%;
		min-height: 100vh;
		background-image: url('/static/images/login/logo-bg.png');
		background-size: 100% 100%;
		
		.title {
			width: 640rpx;
			padding: 158rpx 0 32rpx;
			margin: 0 auto;
			font-size: 46rpx;
			font-weight: bold;
			color: #333333;
		}
		.form {
			width: 640rpx;
			padding: 110rpx 0;
			margin: 0 auto;
			
			.form-item {
				width: 100%;
				height: 104rpx;
				border-radius: 52rpx;
				margin-bottom: 60rpx;
				overflow: hidden;
				background-color: #F9F9F9;
			}
		}
		
		.btn-box {
			width: 640rpx;
			
			// #ifdef APP-PLUS
			margin: 20rpx auto 80rpx;
			// #endif
			// #ifndef APP-PLUS
			margin: 140rpx auto 80rpx;
			// #endif
			
			.btn {
				width: 100%;
				border-radius: 52rpx;
				background-color: $uni-color-error;
				height: 108rpx;
				color: #ffffff;
				
				image {
					width: 46rpx;
					height: 46rpx;
				}
				text {
					font-size: 30rpx;
					margin-left: 11rpx;
				}
			}
		}
		
		.other {
			display: flex;
			align-items: center;
			justify-content: space-around;
			width: 640rpx;
			margin: 0 auto;
			font-size: 24rpx;
			text:nth-of-type(1) {
				color: #0F95BC;
			}
			text:nth-of-type(2) {
				color: #9C9C9C;
			}
		}
	}
	::v-deep .u-input {
		margin-right: 20rpx;
	}
	::v-deep .u-input__input {
		height: 104rpx;
		padding: 0 63rpx;
	}
</style>