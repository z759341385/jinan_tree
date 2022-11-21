<template>
	<view class="tabbar-container">
		<block>
			<view class="tabbar-item" v-for="(item, index) in tabbarList" :class="[item.centerItem ? ' center-item' : '']" @click="changeItem(item)">
				<view class="item-top"><image :src="currentItem == item.id ? item.selectIcon : item.icon"></image></view>
				<view class="item-bottom" :class="[currentItem == item.id ? 'item-active' : '']">
					<text>{{ item.text }}</text>
				</view>
			</view>
		</block>
	</view>
</template>
 
<script>
export default {
	props: {
		currentPage: {
			type: Number,
			default: 0
		}
	},
	data() {
		return {
			currentItem: 0,
			tabbarList: [
				{
					id: 0,
					path: '/pages/index/index',
					icon: '/static/logo.png',
					selectIcon: '/static/logo.png',
					text: '简介',
					centerItem: false
				},
				{
					id: 1,
					path: '/pages/vr/vr',
					icon: '/static/logo.png',
					selectIcon: '/static/logo.png',
					text: 'VR',
					centerItem: false
				},
				{
					id: 2,
					path: '/pages/message/message',
					icon: '/static/logo.png',
					selectIcon: '/static/logo.png',
					text: '扫一扫',
					centerItem: true
				},
				{
					id: 3,
					path: '/pages/message/message',
					icon: '/static/logo.png',
					selectIcon: '/static/logo.png',
					text: '消息',
					centerItem: false
				},
				{
					id: 4,
					path: '/pages/mine/mine',
					icon: '/static/logo.png',
					selectIcon: '/static/logo.png',
					text: '我的',
					centerItem: false
				}
			]
		};
	},
	mounted() {
		this.currentItem = this.currentPage;
		uni.hideTabBar();
	},
	methods: {
		changeItem(item) {
			let _this = this;
			//_this.currentItem = item.id;
			if(item.id==2){
				console.log('--->scanCode');
				this.scanCode()
				return;
			}
			uni.switchTab({
				url: item.path
			});
		},
		scanCode() {
						// 允许从相机和相册扫码
						uni.scanCode({
							scanType: ['qrCode'], //条形码
							success: function(res) {
								console.log(111, res)
		
								// 微信小程序
								if (res.errMsg == "scanCode:ok") {
									// 扫描到的信息
		
									let {
										type,
										code,
										id
									} = JSON.parse(res.result)
		
									// 卖家 取货
									if (type == 'qh') {
										// 跳转到商品详情界面
										uni.navigateTo({
											url: `/reusePage/orderDetails/orderDetails?id=${id}&ordertype=1`
										});
									}
									// uni.showToast({
									// 	title: res.result,
									// 	duration: 2000
									// });
		
								} else {
		
									console.log("未识别到二维码，请重新尝试！")
		
									uni.$u.toast('未识别到二维码，请重新尝试！')
								}
		
							}
						});
					}
	}
};
</script>
<style scoped>
view {
	padding: 0;
	margin: 0;
	box-sizing: border-box;
}
.tabbar-container {
	position: fixed;
	bottom: 0;
	left: 0;
	width: 100%;
	background-color: #ffffff;
	height: calc(100rpx+env(safe-area-inset-bottom));
	box-shadow: 0 0 5px #999;
	display: flex;
	align-items: center;
	padding: 5rpx 0;
	color: #999999;
			padding-bottom: calc(env(safe-area-inset-bottom)) ;
			box-sizing: border-box;
}
.tabbar-container .tabbar-item {
	width: 20%;
	height: 100rpx;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
}
.tabbar-container .item-active {
	color: #f00;
}
.tabbar-container .center-item {
	display: block;
	position: relative;
}
.tabbar-container .tabbar-item .item-top {
	width: 70rpx;
	height: 70rpx;
	padding: 10rpx;
}
.tabbar-container .center-item .item-top {
	flex-shrink: 0;
	width: 100rpx;
	height: 100rpx;
	position: absolute;
	top: -50rpx;
	left: calc(50% - 50rpx);
	border-radius: 50%;
	box-shadow: 0 0 5px #999;
	background-color: #ffffff;
}
.tabbar-container .tabbar-item .item-top image {
	width: 100%;
	height: 100%;
}
.tabbar-container .tabbar-item .item-bottom {
	font-size: 28rpx;
	width: 100%;
}
.tabbar-container .center-item .item-bottom {
	position: absolute;
	bottom: 5rpx;
}
</style>