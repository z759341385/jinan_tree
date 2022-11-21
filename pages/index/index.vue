<template>
	<view class="content">
		<view class="uni-margin-wrap">

			<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
				previous-margin="30rpx" next-margin="30rpx" :duration="duration">
				<swiper-item class="banner-item" v-for="(item ,index) in bannerList" :key="index">
					<image class="banner-image-item" :src="item" mode="scaleToFill" @error="imageError"></image>
				</swiper-item>
			</swiper>
		</view>
		<view class="donate-view-class">
			<button type="primary" @click="scanCode">扫一扫</button>
		</view>
		<view class="place-class">
			<view class="header">
				<text class="header-text">122</text>
				<text class="more-text">更多</text>
			</view>
			<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="120">
				<view class="place-item-class" v-for="(item,index) in places " :key="index">
					<view class="item-class">
						<image class="img-item-class" :src="item.img" mode="scaleToFill" @error="imageError"></image>
						<text class="place-name-class">{{item.name}}</text>
					</view>
				</view>
			</scroll-view>
		</view>


		<view class="pet-class">
			<view class="header">
				<text class="header-text">2</text>
				<text class="more-text">更多</text>
			</view>
			<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="120">
				<view class="pet-item-class" v-for="(item,index) in pets " :key="index">
					<view class="item-class">
						<image class="img-item-class" :src="item.img" mode="scaleToFill" shape="circle"
							@error="imageError"></image>
						<text class="pet-name-class">{{item.name}}</text>
					</view>
				</view>
			</scroll-view>
		</view>
		<view class="pet-class">
			<view class="header">
				<text class="header-text">2</text>
				<text class="more-text">更多</text>
			</view>
			<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="120">
				<view class="pet-item-class" v-for="(item,index) in pets " :key="index">
					<view class="item-class">
						<image class="img-item-class" :src="item.img" mode="scaleToFill" shape="circle"
							@error="imageError"></image>
						<text class="pet-name-class">{{item.name}}</text>
					</view>
				</view>
			</scroll-view>
		</view><view class="pet-class">
			<view class="header">
				<text class="header-text">2</text>
				<text class="more-text">更多</text>
			</view>
			<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="120">
				<view class="pet-item-class" v-for="(item,index) in pets " :key="index">
					<view class="item-class">
						<image class="img-item-class" :src="item.img" mode="scaleToFill" shape="circle"
							@error="imageError"></image>
						<text class="pet-name-class">{{item.name}}</text>
					</view>
				</view>
			</scroll-view>
		</view><view class="pet-class">
			<view class="header">
				<text class="header-text">2</text>
				<text class="more-text">更多</text>
			</view>
			<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="120">
				<view class="pet-item-class" v-for="(item,index) in pets " :key="index">
					<view class="item-class">
						<image class="img-item-class" :src="item.img" mode="scaleToFill" shape="circle"
							@error="imageError"></image>
						<text class="pet-name-class">{{item.name}}</text>
					</view>
				</view>
			</scroll-view>
		</view>
<my-tabbar :current-page="0"></my-tabbar>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				bannerList: [
					'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg',
					'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fd.zdqx.com%2Fqtq_160428%2F001.jpg&refer=http%3A%2F%2Fd.zdqx.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1667839525&t=023e36fbc9844d03b6db9e5640d76841',
					'http://d.zdqx.com/qtq_160428/005.jpg'
				],
				places: [{
						img: 'https://img0.baidu.com/it/u=236085137,1979895699&fm=253&fmt=auto&app=138&f=JPEG?w=360&h=360',
						name: '北京xxxx救助所'
					},
					{
						img: 'https://img0.baidu.com/it/u=236085137,1979895699&fm=253&fmt=auto&app=138&f=JPEG?w=360&h=360',

						name: '2'
					}, {
						img: 'https://img0.baidu.com/it/u=236085137,1979895699&fm=253&fmt=auto&app=138&f=JPEG?w=360&h=360',

						name: '3'
					}, {
						img: 'https://img0.baidu.com/it/u=236085137,1979895699&fm=253&fmt=auto&app=138&f=JPEG?w=360&h=360',

						name: '4'
					},
					{
						img: 'https://img0.baidu.com/it/u=236085137,1979895699&fm=253&fmt=auto&app=138&f=JPEG?w=360&h=360',

						name: '5'
					},

				],
				pets: [{
						img: 'https://img2.baidu.com/it/u=670341883,3643142939&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500',
						name: '蓝猫'
					},
					{
						img: 'https://img0.baidu.com/it/u=236085137,1979895699&fm=253&fmt=auto&app=138&f=JPEG?w=360&h=360',

						name: '2'
					}, {
						img: 'https://img0.baidu.com/it/u=236085137,1979895699&fm=253&fmt=auto&app=138&f=JPEG?w=360&h=360',

						name: '3'
					}, {
						img: 'https://img0.baidu.com/it/u=236085137,1979895699&fm=253&fmt=auto&app=138&f=JPEG?w=360&h=360',

						name: '4'
					},
					{
						img: 'https://img0.baidu.com/it/u=236085137,1979895699&fm=253&fmt=auto&app=138&f=JPEG?w=360&h=360',

						name: '5'
					},

				],
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				scrollTop: 0,
				old: {
					scrollTop: 0
				}
			}
		},
		onLoad() {

		},
		methods: {
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
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
	}
</script>

<style lang="scss">
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding-bottom: calc(150rpx + env(safe-area-inset-bottom));
		.uni-margin-wrap {
			height: 300rpx;
			width: 100%;

			.swiper {
				height: 300rpx;

				.banner-item {
					display: block;
					width: 100%;
					text-align: center;
					height: 300rpx;
					width: cal(100% -60 rpx);

					.banner-image-item {
						height: 300rpx;
						width: 98%;

						border-radius: 30rpx;
					}
				}
			}
		}


		.donate-view-class {
			margin-top: 30rpx;
			width: 80%;
		}

		.place-class {
			margin-top: 40rpx;
			width: 100%;

			.header {
				display: flex;
				flex-direction: row;
				padding-left: 30rpx;
				padding-right: 30rpx;
				justify-content: space-between;
				margin-bottom: 30rpx;

				.header-text {
					font-size: 1.1rem;
				}

				.more-text {
					font-size: 0.8rem;

				}
			}

			.scroll-view_H {
				white-space: nowrap;
				width: 100%;

				.place-item-class {
					display: inline-block;
					text-align: center;
					width: 230rpx;
					margin-left: 30rpx;

					.item-class {
						display: flex;
						flex-direction: column;

						.img-item-class {
							width: 230rpx;
							height: 280rpx;

						}

						.place-name-class {
							margin-top: 16rpx;
							font-size: 0.7rem;

						}
					}
				}
			}


		}

		.pet-class {
			margin-top: 30rpx;
			width: 100%;

			.header {
				display: flex;
				flex-direction: row;
				padding-left: 30rpx;
				padding-right: 30rpx;
				justify-content: space-between;
				margin-bottom: 30rpx;

				.header-text {
					font-size: 1.1rem;
				}

				.more-text {
					font-size: 0.8rem;

				}
			}

			.scroll-view_H {
				white-space: nowrap;
				width: 100%;

				.pet-item-class {
					display: inline-block;
					text-align: center;
					margin-left: 30rpx;

					.item-class {
						display: flex;
						flex-direction: column;

						.img-item-class {
							width: 160rpx;
							height: 160rpx;
							border-radius: 100px;

						}

						.pet-name-class {
							margin-top: 16rpx;
							font-size: 0.7rem;
						}
					}
				}
			}


		}

	}

	// .logo {
	// 	height: 200rpx;
	// 	width: 200rpx;
	// 	margin-top: 200rpx;
	// 	margin-left: auto;
	// 	margin-right: auto;
	// 	margin-bottom: 50rpx;
	// }

	// .text-area {
	// 	display: flex;
	// 	justify-content: center;
	// }

	// .title {
	// 	font-size: 36rpx;
	// 	color: #8f8f94;
	// }

	// .uni-margin-wrap {
	// 	width: 690rpx;
	// 	width: 100%;
	// }



	// .swiper-list {
	// 	margin-top: 40rpx;
	// 	margin-bottom: 0;
	// }

	// .uni-common-mt {
	// 	margin-top: 60rpx;
	// 	position: relative;
	// }

	// .info {
	// 	position: absolute;
	// 	right: 20rpx;
	// }

	// .uni-padding-wrap {
	// 	width: 550rpx;
	// 	padding: 0 100rpx;
	// }
</style>
