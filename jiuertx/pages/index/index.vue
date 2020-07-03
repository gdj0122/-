<template>
	<view class="contentx">
		<view class="top-bar">
			<view class="top-bar-left">
				<image src="../../static/image/img/l.png" mode=""></image>
			</view>
			<view class="top-bar-center">
				<image src="../../static/image/index/火@2x.png" mode=""></image>
			</view>
			<view class="top-bar-right">
				<view class="add">
					<image src="../../static/image/index/add group@2x.png" mode=""></image>
				</view>
				<view class="secrch">
					<image src="../../static/image/index/search@2x.png" mode=""></image>
				</view>
			</view>
		</view>
		<view class="main">
			<view class="apply friends">
				<view class="friends-list">
					<view class="friends-list-l">
						<text class="tip">1</text>
						<image src="../../static/image/img/q.png" mode=""></image>
					</view>
					<view class="friends-list-r">
						<view class="top">
							<view class="name">好友申请</view>
							<view class="time">14:30</view>
						</view>
						<view class="content">快来一起吃鸡</view>
					</view>
				</view>
			</view>
			<view class="friends">
				<view class="friends-list" v-for="(item,index) in friends" :key="index">
					<view class="friends-list-l">
						<text class="tip">{{item.tip}}</text>
						<image :src='`../../static/image/img/${item.imgUrl}`' mode=""></image>
					</view>
					<view class="friends-list-r">
						<view class="top">
							<view class="name">{{item.name}}</view>
							<view class="time">{{change(item.time)}}</view>
						</view>
						<view class="content">{{item.news}}</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import datas from '../../commons/js/datats.js'
	import myfen from '../../commons/js/myfun.js'
	export default {
		data() {
			return {
				friends:[]
			}
		},
		onLoad() {
			this.getFineds()
		},
		methods: {
			change(data){
				return myfen.dateTime(data)
			},
			getFineds(){
				this.friends = datas.frineds()
				console.log(this.friends)
			}
		}
	}
</script>

<style lang="scss">
	.contentx {
		padding-top: var(--status-bar-height);
		.top-bar{
			display: flex; 
			justify-content: space-between;
			align-items: center;
			width: 100%;
			height: 88rpx;
			background: $uni-bg-color;
			border-bottom: $uni-border-color;
			box-shadow: 0 1px 0 0 rgba(0,0,0,.1);
			// padding-left: $uni-spacing-col-base;
			// padding-right: $uni-spacing-col-base;
			box-sizing: border-box;
			padding-top: var(--status-bar-height);
			.top-space {
				width: 100%;
				height: var(--status-bar-height);
			}
			.top-bar-left{
				padding-left: $uni-spacing-col-base;
				flex: 1;
				image{
					width: 68rpx;
					height: 68rpx;
					border-radius:16px;
				}
			}
			.top-bar-center{
				flex: 1;
				image{
					width: 88rpx;
					height: 68rpx;
				}
			}
			.top-bar-right{
				flex: 1;
				.secrch{
					width: 88rpx;
					height: 88rpx;
					display: inline-block;
					float: right;
				}
				.add{
					width: 88rpx;
					height: 88rpx;
					display: inline-block;
					float: right;
				}
				image{
					padding: 18rpx 0 0 18rpx;
					width: 52rpx;
					height: 52rpx;
				}
			}
		}
		.main{
			padding:$uni-spacing-col-base;
			.apply{}
			.friends{
				.friends-list{
					display: flex;
					padding: 20rpx 0;
					&:active{
						background-color: $uni-bg-color-grey;
					}
					.friends-list-l{
						position: relative;
						width: 96rpx;
						height: 96rpx;
						image{
							width: 96rpx;
							height: 96rpx;
							border-radius: $uni-border-radius-lg;
							background-color: $uni-bg-color;
						}
						.tip{
							position: absolute;
							top: -6rpx;
							z-index: 5;
							right: 0;
							min-width: 36rpx;
							height: 36rpx;
							line-height: 36rpx;
							border-radius: $uni-border-radius-circle;
							background: red;
							font-size: $uni-font-size-sm;
							text-align: center;
							color: $uni-text-color-inverse;
						}
					}
					.friends-list-r{
						flex: 1;
						padding-left: $uni-spacing-col-base;
						.top{
							display: flex;
							justify-content: space-between;
							.name{
								flex: 1;
								font-size: 36rpx;
								font-weight: 400;
								color: $uni-text-color;
							}
							.time{
								flex: 1;
								text-align: right;
								font-size: $uni-font-size-sm;
								color: $uni-text-color-disable;
							}
						}
						.content{
							font-size: $uni-font-size-base;
							color: $uni-text-color-grey;
							line-height: 40rpx;
							overflow: hidden;
							text-overflow: ellipsis;
							white-space: nowrap;
						}
					}
				}
			}
		}
	}
</style>
