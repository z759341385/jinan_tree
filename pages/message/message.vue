<template>
	<view class="page">
		<scroll-view class="scroll-view" scroll-y="false" refresher-enabled="true" :refresher-triggered="triggered"
			:refresher-threshold="100" refresher-background="lightgreen" @refresherpulling="onPulling"
			@refresherrefresh="onRefresh" @refresherrestore="onRestore" @refresherabort="onAbort" @scrolltolower="lower"
			@scroll="scroll">
			<view class="message-item-class" v-for="(item,index) in messages">{{item.userName}}</view>

		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				triggered: false,
				messages: [{
						userName: '小明'
					}, {
						userName: '小黄'
					},
					{
						userName: '小丽'
					},
		
				]
			}
		},
		onLoad() {
			this._freshing = false;
			setTimeout(() => {
				this.triggered = true;
			}, 1000)
		},
		methods: {

			onPulling(e) {
				console.log("onpulling", e);
			},
			onRefresh() {
				if (this._freshing) return;
				this._freshing = true;
				setTimeout(() => {
					this.triggered = false;
					this._freshing = false;
				}, 1000)
				this.messages.push({userName:'刷新新消息+1'});
			},
			onRestore() {
				this.triggered = 'restore'; // 需要重置
				console.log("onRestore");
			},
			onAbort() {
				console.log("onAbort");
			},
		},
	}
</script>

<style lang="scss">
	.page {
		max-height: 100%;
		width: 100%;

		.scroll-view {
			min-height: 1000rpx;
			background-color: aqua;
			.message-item-class {
				width: 100%;
				height: 100rpx;
				margin-top: 30rpx;
				background-color: gainsboro;
			}
		}
	}
</style>
