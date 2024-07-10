<template>
	<view class="content">
		<view class="logo">
			<image src="https://v1.uviewui.com/common/logo.png" mode="widthFix"></image>
		</view>
		<view class="phone">177****8888</view>
		<view class="subTitle">认证服务由中国电信提供</view>
		<view class="btn-box">
			<view class="btn u-flex u-row-center u-col-center">
				<text>本机号码一键登录</text>
			</view>
		</view>
		<view class="check u-flex u-row-center u-col-center">
			<u-checkbox-group>
				<u-checkbox v-model="checked" shape="circle" active-color="#BC1C0F"></u-checkbox>
			</u-checkbox-group>
			<text>登录即同意</text>
			<text>《服务和隐私协议》</text>
			<text>并授权获取和验证</text>
		</view>
		<view class="other u-flex u-row-center u-col-center">
			<view class="nav" @click="toUrl('/pages/login/login-pwd')">
				<u-icon name="lock-open" size="49" color="#0F95BC"></u-icon>
			</view>
			<view class="line"></view>
			<view class="nav">
				<image src="/static/images/login/wechat-icon.png" mode="widthFix"></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				checked: true
			}
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
		width: 100%;
		min-height: 100vh;
		background-image: url('/static/images/login/logo-bg.png');
		background-size: 100% 100%;
		
		.logo {
			padding-top: 138rpx;
			text-align: center;
			image {
				width: 190rpx;
				height: 190rpx;
			}
		}
		
		.phone {
			padding-top: 70rpx;
			font-weight: bold;
			font-size: 54rpx;
			color: #333333;
			text-align: center;
		}
		
		.subTitle {
			color: #999999;
			font-size: 24rpx;
			padding-top: 33rpx;
			text-align: center;
		}
		
		.btn-box {
			width: 640rpx;
			margin: 264rpx auto 80rpx;
			
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
		
		.check {
			text {
				color: #999999;
				font-size: 24rpx;
			}
			text:nth-of-type(2) {
				color: $uni-color-error;
			}
			
			.u-checkbox-group {
				width: 48rpx;
			}
		}
		
		.other {
			margin: 124rpx 0 0;
			
			.nav {
				width: 103rpx;
				height: 103rpx;
				border-radius: 50%;
				display: flex;
				align-items: center;
				justify-content: center;
				background-color: #F3F3F3;
				border-right: 2px solid #F3F3F3;
				margin: 0 89rpx;
				
				image {
					width: 52rpx;
					height: 42rpx;
				}
			}
			.line {
				width: 4rpx;
				height: 59rpx;
				border-radius: 5rpx;
				background-color: #F3F3F3;
			}
		}
	}
</style>