<template>
	<view class="home">
		<!-- interval-切换时间 -->
		<swiper indicator-dots circular autoplay interval="1000">
			<swiper-item><image src="https://img.zcool.cn/community/015fad5543c75f0000019ae931ebe5.jpg@1280w_1l_2o_100sh.jpg"></image></swiper-item>
			<swiper-item><image src="http://gd-hbimg.huaban.com/428cb9d7ae53f4cbfe37e40134ad176512993adf2cde6-0DtsGN"></image></swiper-item>
			<swiper-item><image src="https://img.zcool.cn/community/01610556de68d832f875520f959e2a.jpg@2o.jpg"></image></swiper-item>
		</swiper>
		<view class="nav">
			<view class="nav_item" v-for="(item,index) in navs" :key="index" @click="navItemClick(item.path)">
				<!-- <view><svg class="icon" aria-hidden="true"><use xlink:href="#item.icon"></use></svg></view> -->
				<view :class="item.icon"></view>
				<text>{{item.title}}</text>
			</view>
		</view>
		<view class="hot_goods">
			<view class="tit">推荐商品</view>
			<Goods @laile='shoudo' :god='pic' @woyoulaile='goGoodsDtail'></Goods>
		</view>
	</view>
</template>

<script>
	import Goods from '@/pages/components/good-list/goods-list.vue'
	export default {
		components:{
			Goods,
		},
		data(){
			return {
				pic:[],
				navs:[
					{
						icon:'iconfont icon-gouwu',
						title:'湘甜超市',
						path:'/pages/goods/goods'
					},
					{
						icon:'iconfont icon-tongzhi',
						title:'联系我们',
						path:'/pages/contact/contact'
					},
					{
						icon:'iconfont icon-xiangce',
						title:'社区图片',
						path:'/pages/pics/pics'
					},
					{
						icon:'iconfont icon-shexiangji',
						title:'学习视频',
						path:'/pages/videos/videos'
					}
				]
			}
		},
		onLoad() {
			
		},
		methods:{
			navItemClick(url){
				// console.log(url)//test
				uni.navigateTo({
					url:url
				})
			},
			shoudo(ayya){
				this.pic = ayya
			},
			goGoodsDtail(){
				uni.navigateTo({
					url:'/pages/goods-detail/goods-detail'
				})
			}
		}
	}
</script>

<style lang="scss">
	.home {
		swiper {
			width: 750rpx;
			height: 350rpx;
			image {
				height: 100%;
				width: 100%;
			}
		}
		.nav {
			display: flex;
			.nav_item {
				width: 50%;
				text-align: center;
				view {
					width:120rpx;
					height: 120rpx;
					background-color: $shop-color;
					color: #FFC0CB;
					font-size: 80rpx;
					border-radius: 60rpx;
					margin: 10px auto;
					line-height: 120rpx;
				}
				text {
					font-size: 40rpx;
				}
			}
		}
		.hot_goods {
			background-color: #BBFFFF;
			overflow: hidden;
			margin-top: 10px;
			.tit {
				height: 50px;
				line-height: 50px;
				color: #6495ED;
				text-align: center;
				letter-spacing: 20rpx;//字间距
				background-color: #fff;
				margin: 7rpx 0;
				
			}
		}
	}
</style>