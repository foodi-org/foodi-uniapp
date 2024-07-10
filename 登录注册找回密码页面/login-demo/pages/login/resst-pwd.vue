<template>
	<view class="content">
		<view class="title">重置密码</view>
		<view class="subTitle">6-20位字符，请使用数字+字母</view>
		<view class="form">
			<view class="form-item">
				<u-input v-model="form.pwd" type="password" placeholder="请输入密码"/>
			</view>
		</view>
		<view class="btn-box">
			<view class="btn u-flex u-row-center u-col-center">
				<text>完成</text>
			</view>
		</view>
		
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				form: {
					pwd: ''
				},
			}
		},
		methods: {
			
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
		.subTitle {
			width: 640rpx;
			margin: 0 auto;
			font-size: 23rpx;
			color: #999999;
		}
		.form {
			width: 640rpx;
			padding: 54rpx 0;
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
			margin: 266rpx auto 0;
			// #endif
			// #ifndef APP-PLUS
			margin: 386rpx auto 0;
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
	}
	::v-deep .u-input {
		width: 92%;
	}
	::v-deep .u-input__input {
		width: 90%;
		height: 104rpx;
		padding: 0 63rpx;
	}
</style>