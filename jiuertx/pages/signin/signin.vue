<template>
	<view class="	">
			<view class="top-bar">
				<view class="top-bar-right">
					<view class="text">注册</view>
				</view>
			</view>
			<view class="logo">
				<image src="../../static/image/sign/logo1.png" mode=""></image>
			</view>
			<view class="main">
				<view class="title">登录</view>
				<view class="slogan">您好,欢迎来到酒儿通信</view>
				<view class="inputs">
					<input type="text" placeholder="用户名/邮箱" placeholder-style="color:#aaa;font-weight:400" class="user"/>
					<input type="password" placeholder="密码" placeholder-style="color:#aaa;font-weight:400" class="psw"/>
				</view>
				<view class="tips">输入用户或者密码错误!</view>
			</view>
			<view class="submit">登录</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.content{
		text-align: center;
	}
	.top-bar{
		height: 88rpx;
		line-height: 88rpx;
		background: $uni-bg-color;
		box-shadow: 0 1px 0 0 rgba(0,0,0,.1);
		padding-top: var(--status-bar-height);
		.top-bar-right{
			float: right;
			padding-right: 32rpx;
			.text{
				font-size: $uni-font-size-lg;
				font-weight: 500;
				color: $uni-text-color;
				line-height: 88rpx;
			}
		}
	}
	.logo{
		text-align: center;
		image{
			padding-top: 256rpx;
			width: 194rpx;
			height: 92rpx;
			margin: 0 auto;
		}
	}
	.main{
		padding: 54rpx $uni-spacing-row-lg 120rpx;
		// width: 100%;
		.title{
			font-size: 56rpx;
			font-weight: 500;
			color: $uni-text-color;
			line-height: 88rpx;
		}
		.slogan{
			font-size: 40rpx;
			color: $uni-text-color-grey;
			line-height: 56rpx;
		}
		.inputs{
			padding-top: 8rpx;
			input{
				padding-top: 40rpx;
				height: 88rpx;
				font-size: 	$uni-font-size-lg;
				font-weight: 500;
				color: $uni-text-color;
				line-height: 88rpx;
				border-bottom: 1px solid $uni-border-color;
			}
		}
		.tips{
			float: left;
			font-size: 	$uni-font-size-lg;
			color: $uni-color-warning;
			line-height: 56rpx;
		}
	}
	.submit{
		width: 520rpx;
		height: 96rpx;
		margin: 0 auto;
		background: $uni-color-primary;
		box-shadow: 0 50rpx 32px -36px rgba(255,228,49,0.40);
		border-radius: 48rpx;
		text-align: center;
		font-size: $uni-font-size-lg;
		font-family: PingFangSC-Medium;
		font-weight: 500;
		color: $uni-text-color;
		line-height:96rpx;
	}
</style>
