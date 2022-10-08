<template>
	<view class="content">
		<view class="uni-margin-wrap">

			<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
				previous-margin="30rpx" next-margin="30rpx" :duration="duration">
				<swiper-item   class="banner-item" v-for="(item ,index) in bannerList" :key="index">
					<image class="banner-image-item" :src="item" mode="scaleToFill" @error="imageError"></image>
				</swiper-item>
			</swiper>
		</view>
		<view class="donate-view-class">
			<button type="primary">捐步数1</button>
		</view>
		<view class="place-class">
			<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="120">
				<view class="place-item-class" v-for="(item,index) in places " :key="index">
					{{item.name}}
				</view>
			</scroll-view>
		</view>

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
						name: '1'
					},
					{
						name: '2'
					}, {
						name: '3'
					}, {
						name: '4'
					},
					{
						name: '1'
					},
					{
						name: '2'
					}, {
						name: '3'
					}, {
						name: '4'
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
		}
	}
</script>

<style lang="scss">
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;

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
					.banner-image-item{
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
			margin-top: 30rpx;

			width: 100%;
			height: 100px;

			.scroll-view_H {
				white-space: nowrap;
				width: 100%;

				.place-item-class {
					display: inline-block;
					text-align: center;
					background-color: #00aa7f;
					width: 100px;
					height: 100px;
					margin-left: 30px;
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
