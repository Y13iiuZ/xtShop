<template>
	<view class="contact">
		<image class="imgs" src="../../static/联系我们.png"></image>
		<view class="info">
			<view @click="phone">联系电话: 18381037727 (点击拨打)</view>
			<view>联系地址： 四川省成都市成华区北京字节跳动信息技术有限公司</view>
		</view>
		<map class="map" :longitude="longitude" :latitude="latitude" :markers="markers" :scale="scale"></map>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				longitude:103.60298,
				latitude:30.894435,
				scale:13,
				markers:[
					{
						longitude:103.60298,
						latitude:30.894435,
						iconPath:'../../static/外星球2.png',
						width:50,
						height:50
					}
				]
			}
		},
		methods: {
			phone(){
				uni.makePhoneCall({
					phoneNumber:'18381037727'
				})
			}
		}
	}
</script>

<style lang="scss">
	.contact {
		.imgs {
			width: 750rpx;
			height: 320rpx;
		}
		.info {
			padding: 10rpx 20rpx;
			font-size: 30rpx;
			view {
				line-height: 80rpx;
				border-bottom: 1px solid #eee;
			}
		}
		.map {
			width: 750rpx;
			height: 750rpx;
		}
	}
</style>
