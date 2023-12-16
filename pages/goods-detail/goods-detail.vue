<template>
	<view class="goods_details">
		<swiper indicator-dots>
			<swiper-item v-for="(item,index) in navis" :key='index'>
				<image :src="item.srcs"></image>
			</swiper-item>
		</swiper>
		<view class="box1">
			<view class="price">
				<text>￥6799</text>
				<text>￥9788</text>
			</view>
			<view class="goods_name">iPhone 14 Pro Max 5G手机 （全网通）</view>
		</view>
		<view class="line"></view>
		<view class="box2">
			<view>货号：232217889924226</view>
			<view>库存：3677</view>
		</view>
		<view class="line"></view>
		<view class="box3">
			<view class="tit">详细介绍</view>
			<view class="content">{{contentData}}</view>
		</view>
	</view>
	<view class="goods_button">
		<uni-goods-nav :buttonGroup='buttonGroup' :fill="true" :options="options" @click="onclick" @buttonClick="buttonClick"></uni-goods-nav>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				id:0,
				navis:[
					{
						srcs:'https://store.storeimages.cdn-apple.com/8756/as-images.apple.com/is/iphone14promax-digitalmat-gallery-1-202209?wid=364&hei=333&fmt=png-alpha&.v=1676512715573',
						name:'14one'
					},
					{
						srcs:'https://store.storeimages.cdn-apple.com/8756/as-images.apple.com/is/iphone14promax-digitalmat-gallery-2-202209?wid=364&hei=333&fmt=png-alpha&.v=1660830896851',
						name:'14two'
					},
					{
						srcs:'https://store.storeimages.cdn-apple.com/8756/as-images.apple.com/is/iphone14promax-digitalmat-gallery-3-202209_GEO_CN?wid=364&hei=333&fmt=png-alpha&.v=1664837257771',
						name:'14three'
					}
				],
				contentData:`1.更明亮的 6.7 英寸超视网膜 XDR 显示屏¹，支持全天候显示，有消息随时看得见
				2.灵动岛功能，iPhone 的新玩法 3.车祸检测功能可检测到严重车祸，并主动拨打求救电话² 4.4800 万像素主摄，配备先进的四合一像素传感器，可将分辨率提升至最高 4 倍
				5.A16 仿生芯片速度超快，能效超高，带来从早用到晚的电池续航以 iPhone 或
				现有手机来换购，
				享受折抵优惠。
				用 iPhone 11 或后续机型来换购，预计可享 RMB 1200 至 RMB 5250 的折抵优惠*。可享最长 24 个月免息分期8。
				通过指定的合作伙伴，你可以选择适合自己的分期付款方案。循环利用，
				打开新思路力保个人信息安全，这很 iPhone iPhone人人可用。`,
				buttonGroup: [{
					      text: '加入购物车',
					      backgroundColor: '#6495ed',
					      color: '#fff'
					    },
					    {
					      text: '立即购买',
					      backgroundColor: '#ff0000',
					      color: '#fff'
					    }
				],
				 options: [{
							icon: 'headphones',
							text: '客服'
						}, {
							icon: 'shop',
							text: '店铺',
							info: 5,
							infoBackgroundColor:'#007aff',
							infoColor:"red"
						}, {
							icon: 'cart',
							text: '购物车',
							info: 9
						}]
			}
		},
		methods: {
			 onClick (e) {
				    // uni.showToast({
				    //   title: `点击${e.content.text}`,
				    //   icon: 'none'
				    // })
					console.log(e)
				  },
				  buttonClick (e) {
				    console.log(e)
				    this.options[2].info++
				  }
		}
	}
</script>

<style lang="scss">
	.goods_details {
		swiper {
			height: 700rpx;
			image {
				width: 100%;
				height: 100%;
			}
		}
		.box1 {
			padding: 10px;
			.price {
				font-size: 40rpx;
				line-height: 80rpx;
				color: $shop-color;
				text:nth-child(2) {
					color: #FF4500;
					font-size: 28rpx;
					margin-left: 20rpx;
					text-decoration: line-through;
				}
			}
			.goods_name {
				font-size: 32rpx;
				line-height: 60rpx;
			}
		}
		.box2 {
			padding: 0 10rpx;
			font-size: 32rpx;
			line-height: 80rpx;
		}
		.box3 {
			.tit {
				font-size: 32rpx;
				padding-left: 10rpx;
				border-bottom: 1px solid #eee;
				line-height: 70rpx;
			}
			.content {
				padding: 10px;
				font-size: 28rpx;
				color: #000000;
			}
		}
	}
	.line {
		width: 750rpx;
		height: 10rpx;
		background: #eee;
	}
	.goods_button {
		position: fixed;
		bottom: 0;
		width: 100%;
	}
</style>
