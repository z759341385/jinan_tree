<template>
	<view>
		<div class="mineTop">
			<div class="topBc"></div>
			<div class="userInfo">
				<image src="../../static/userHead.png" class="userImg"></image>
				<h1 class="userName">{{userInfo.userName}}</h1>
			</div>
		</div>
		<div class="track">
			<div class="trackIcon">
				<image src="../../static/mineTrack.png" class="trackImg"></image>
			</div>
			<h1 class="trackText">轨迹</h1>
		</div>
		<div class="greyLine"></div>
		<div @click="onActive(item.page)" v-for="(item,index) in activeList" class="activeItem">
			<image :src="item.icon" class="itemIcon"></image>
			<h1 class="itemTitle">{{item.title}}</h1>
		</div>
		<my-tabbar :current-page="4"></my-tabbar>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userInfo:{
					userName:"曼联是信仰",
					userIcon:"/static/userHead.png"
				},
				activeList:[
					{
						title:"修改密码",
						page:"",
						icon:"/static/minePassword.png"
					},
					{
						title:"关于",
						page:"",
						icon:"/static/mineAbout.png"
					},
					{
						title:"更新",
						page:"",
						icon:"/static/mineUpdate.png"
					}
				]
			}
		},
		methods: {
			onActive(page){
				console.log("点击",page);
			}
		}
	}
</script>

<style lang="scss">
	.mineTop{
		background-color: #ffffff;
		height: 300rpx;
		position: relative;
		.topBc{
			background-color: #607b6c;
			height: 180rpx;
			width: 100%;
		}
		.userInfo{
			position: absolute;
			bottom: 0;
			height: 150rpx;
			display: flex;
			left: 20rpx;
			align-items: center;
			.userImg{
				border-radius: 50rpx;
				width: 150rpx;
				height: 150rpx;
				margin-right: 20rpx;
			}
			.userName{
				color: #000000;
				font-size: 20px;
				font-weight: 600;
			}
		}
		
	}
	.track{
		margin-top: 24px;
		margin-left: 20rpx;
		display: inline-block;
		text-align: center;
		.trackIcon{
			width: 80rpx;
			height: 80rpx;
			border-radius: 8rpx;
			margin-bottom: 12rpx;
			position: relative;
			box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
			.trackImg{
				width: 50rpx;
				height: 50rpx;
				position: absolute;
				top: 15rpx;
				left: 15rpx;
			}
		}
		.trackText{
			font-size: 14px;
			color: #333;
			font-weight: 400;
		}
	}
	.greyLine{
		height: 32rpx;
		width: 100%;
		margin-top: 32rpx;
		background-color: #f8f8f8;
	}
	.activeItem{
		padding: 20rpx;
		display: flex;
		align-items: center;
		.itemIcon{
			width: 40rpx;
			height: 40rpx;
			margin-right: 20rpx;
		}
		.itemTitle{
			font-size: 28rpx;
			color: #0d4356;
			font-weight: 400;
		}
	}
	
</style>
