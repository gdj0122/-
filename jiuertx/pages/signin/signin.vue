<template>
	<view>
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
					<input type="text" placeholder="用户名/邮箱	" />
				</view>
			</view>
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
	.top-bar{
		height: 88rpx;
		line-height: 88rpx;
		background: $uni-bg-color;
		box-shadow: 0 1px 0 0 rgba(0,0,0,.1);
		padding-top: var(--status-bar-height);
		.top-bar-right{
			float: right;
			padding-right: :;rpx;
			.text{
				font-size: $uni-font-size-lg;
				font-weight: 500;
				color: $uni-text-color;
				line-height: 88rpx;
			}
			}
		}
</style>
