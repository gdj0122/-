<template>
	<view class="">
			<view class="top-bar">
				<view class="top-bar-left">
					<image class="back-img" src="../../static/image/common/back.svg" mode=""></image>
				</view>
			</view>
			<view class="logo">
				<image src="../../static/image/sign/logo1.png" mode=""></image>
			</view>
			<view class="main">
				<view class="title">注冊</view>
				<view class="inputs">
					<view class="inputs-div">
						<input type="text" placeholder="昵称" placeholder-style="color:#aaa;font-weight:400" class="user"/>
						<view class="employ" v-if="employ">已占用</view>
						<image src="../../static/image/sign/ok.png" class="ok" mode="" v-if="isuser"></image>
					</view>
					<view class="inputs-div">
						<input type="text" placeholder="邮箱" placeholder-style="color:#aaa;font-weight:400" class="email" @blur="isEmail"/>
						<view class="employ" v-if="employ">已占用</view>
						<view class="invalid" v-if="invalid">邮箱无效</view>
						<image src="../../static/image/sign/ok.png" class="ok" mode="" v-if='isemail'></image>
					</view>
					<view class="inputs-div">
						<input :type="type" placeholder="密码" placeholder-style="color:#aaa;font-weight:400" class="psw"/>
						<view class="employ" v-if="employ">已占用</view>
						<image :src="lookUrl" mode="" class="look" @tap="looks"></image>
					</view>
				</view>
			</view>
			<view class="submit">登录</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				type:"password",
				isuser:true,
				isemail:false,
				look:true,
				invalid:false,
				employ:false,
				lookUrl:'../../static/image/sign/biyan.png',
				email:null
			}
		},
		methods: {
			looks (){
				if (this.look==true) {
					this.type='text'
					this.lookUrl='../../static/image/sign/查看@2x.png'
				}else{
					this.type='password'
					this.lookUrl='../../static/image/sign/biyan.png'
				}
					this.look = !this.look
				console.log(this.look)
			},
			// 判斷郵箱
			isEmail(e){
				this.email = e.detail.value
				let reg = /^([a-zA-Z]|[0-9])(\w|\-)+@[a-zA-Z0-9]+\.([a-zA-Z]{2,4})$/;
				if(this.email.length>0){
					if(reg.test(this.email)){
						this.invalid=false
					}else{
						this.invalid=true
					}
				}
			}
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
		.top-bar-left{
			float: left;
			padding: 0 32rpx;
			.text{
				font-size: $uni-font-size-lg;
				font-weight: 500;
				color: $uni-text-color;
				line-height: 88rpx;
			}
			.back-img{
				width: 26rpx;
				height: 46rpx;
				margin-top: 21rpx;
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
		.inputs-div{
			position: relative;
		}
		.employ,.invalid{
			position: absolute;
			right: 0;
			bottom: 0;
			float: right;
			font-size: $uni-font-size-base;
			font-weight: 500;
			color: $uni-color-warning;
			line-height: 88rpx;
		}
		.ok{
			position: absolute;
			right: 0;
			bottom: 10rpx;
			width: 42rpx;
			height: 32rpx;
		}
		.look{
			position: absolute;
			right: 0;
			bottom: 10rpx;
			width: 64rpx;
			height: 40rpx;
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
