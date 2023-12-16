<template>
	<view class="news" @click="goDetail()">
		<view class="news_item">
			<image src="http://gd-hbimg.huaban.com/428cb9d7ae53f4cbfe37e40134ad176512993adf2cde6-0DtsGN"></image>
			<view class="right">
				<view class="tit">
					阿打算将大大萨达所大所asodjasodasodjoasgdsfgdafjojifa大家啊搜救队
				</view>
				<view class="info">
					<text>发表时间：2023年4月18日</text>
					<text>浏览：999次</text>
				</view>
			</view>
		</view>
		<view class="news_item">
			<image src="http://gd-hbimg.huaban.com/428cb9d7ae53f4cbfe37e40134ad176512993adf2cde6-0DtsGN"></image>
			<view class="right">
				<view class="tit">
					阿打算将大大萨达所大所asodjasodasodjoasgdsfgdafjojifa大家啊搜救队
				</view>
				<view class="info">
					<text>发表时间：2023年4月18日</text>
					<text>浏览：999次</text>
				</view>
			</view>
		</view>
		<view class="news_item">
			<image src="http://gd-hbimg.huaban.com/428cb9d7ae53f4cbfe37e40134ad176512993adf2cde6-0DtsGN"></image>
			<view class="right">
				<view class="tit">
					阿打算将大大萨达所大所asodjasodasodjoasgdsfgdafjojifa大家啊搜救队
				</view>
				<view class="info">
					<text>发表时间：{{time}}</text>
					<text>浏览：999次</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data(){
			return {
				nian:2023,
				yue:3,
				ri:5,
				time:''
			}
		},
		onLoad() {
			this.time = `${this.nian}-${this.yue.toString().padStart(2,0)}-${this.ri.toString().padStart(2,0)}`//转行成几位 不满足就加0
		},
		methods:{
			goDetail(){
				uni.navigateTo({
					url:'/pages/detail/detail'
				})
			}
		}
	}
</script>

<style lang="scss">
	.news {
		.news_item {
			display: flex;
			word-break: break-all;
			padding: 10rpx 20rpx;
			border-bottom: 1px solid $shop-color;
			image {
				min-width: 200rpx;
				max-width: 200rpx;
				height: 150rpx;
			}
			.right {
				margin-left: 15rpx;
				display: flex;
				flex-direction: column;
				justify-content: space-between;
				.tit {
					font-size: 30rpx;
				}
				.info {
					font-size: 24rpx;
					text:nth-child(2) {
						margin-left: 30rpx;
					}
				}
			}
		}
	}
</style>