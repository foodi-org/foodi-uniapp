<template>
	<view class="content">
		<view class="title">验证码登录</view>
		<view class="form">
			<view class="form-item">
				<u-input v-model="form.phone" type="number" placeholder="请输入手机号"/>
			</view>
			<view class="form-item">
				<u-input v-model="form.code" placeholder="请输入验证码"/>
				<text class="code-text" @click="getCode" :style="{'color': codeTips=='重新获取验证码'?'#BC1C0F':'#333333'}">{{codeTips}}</text>
			</view>
		</view>
		<view class="btn-box">
			<view class="btn u-flex u-row-center u-col-center">
				<text>登录</text>
			</view>
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
				form: {
					phone: '',
					code: ''
				},
				codeTips: '获取验证码',
				count: 60,
				timer: null
			}
		},
		methods: {
			toUrl(url) {
				uni.redirectTo({
					url: url
				})
			},
			getCode() {
				if(this.count != 60) return
				this.count--;
				this.codeTips = `倒计时${this.count}s`
				this.timer = setInterval(() => {
					this.count--;
					this.codeTips = `倒计时${this.count}s`
					if(this.count == 0) {
						this.count = 60;
						this.codeTips = '重新获取验证码';
						clearInterval(this.timer);
					}
				}, 1000)
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
				position: relative;
				width: 100%;
				height: 104rpx;
				border-radius: 52rpx;
				margin-bottom: 60rpx;
				overflow: hidden;
				background-color: #F9F9F9;
				
				.code-text {
					position: absolute;
					display: inline-block;
					flex: 1;
					height: 100%;
					width: 200rpx;
					text-align: center;
					line-height: 104rpx;
					padding-right: 20rpx;
					z-index: 1;
					right: 0;
					top: 0;
					color: #333333;
					font-size: 24rpx;
					background-color: #F9F9F9;
				}
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
	::v-deep .u-input {
		margin-right: 20rpx;
	}
	::v-deep .u-input__input {
		height: 104rpx;
		padding: 0 63rpx;
	}
	::v-deep .form-item:nth-of-type(2) .u-input__input {
		margin-right: 200rpx;
	}
</style>