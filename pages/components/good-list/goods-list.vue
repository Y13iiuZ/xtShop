<template>
	<view class="goods_list" @click="navGO">
		<view class="good_item" v-for="(item,index) in god" :key="index">
			<img :src="item.srcs" width="180" height="200" />
			<view class="price">
				<text>￥{{item.nowPrice}}</text>
				<text>￥{{item.oldPrice}}</text>
			</view>
			<view class="names">
				{{item.texts}}
			</view>
		</view>
		<view class="good_item" v-for="(item,index) in god" :key="index">
			<img :src="item.srcs" width="180" height="200" />
			<view class="price">
				<text>￥{{item.nowPrice}}</text>
				<text>￥{{item.oldPrice}}</text>
			</view>
			<view class="names">
				{{item.texts}}
			</view>
		</view>
		<view class="good_item" v-for="(item,index) in god" :key="index">
			<img :src="item.srcs" width="180" height="200" />
			<view class="price">
				<text>￥{{item.nowPrice}}</text>
				<text>￥{{item.oldPrice}}</text>
			</view>
			<view class="names">
				{{item.texts}}
			</view>
		</view>
		<view class="good_item" v-for="(item,index) in god" :key="index">
			<img :src="item.srcs" width="180" height="200" />
			<view class="price">
				<text>￥{{item.nowPrice}}</text>
				<text>￥{{item.oldPrice}}</text>
			</view>
			<view class="names">
				{{item.texts}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:['god'],
		data(){
			return {
				goodsitem:[
					{
						srcs:'../../../static/iphone14.jpg',
						nowPrice:7999,
						oldPrice:8999,
						texts:'全新iPhone 14 Prodada dadada dadadadadada'
					},
					{
						srcs:'../../../static/iphone13pro.jpeg',
						nowPrice:7999,
						oldPrice:8999,
						texts:'全新iPhone 13 Prodada dadada dadadadadada'
					},
					{
						srcs:'../../../static/iphone12.jpg',
						nowPrice:7999,
						oldPrice:8999,
						texts:'全新iPhone 12 Prodada dadada dadadadadada'
					},
					
				]
			}
		},
		methods:{ 
			hei(){
			this.$emit('laile',this.goodsitem);
			},
			navGO(){
				this.$emit('woyoulaile')
			}
		},
		created() {
			this.$emit('laile',this.goodsitem);
		}
	}
</script>

<style lang="scss">
	.goods_list {
		padding: 0 15rpx;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		.good_item {
			background-color: #fff;
			width: 355rpx;
			margin: 10rpx 0;
			padding: 15rpx;
			box-sizing: border-box;
			image {
				width:80%;
				height: 150rpx;
				display: block;
				margin: auto;
			}
			.price {
					color: #6495ED;
					font-size: 36rpx;
					margin: 20rpx 0 10rpx 0;
					text:nth-child(2) {
						color: #FF4500;
						font-size: 28rpx;
						text-decoration: line-through;
						margin-left: 15rpx;
					}
			}
			.names {
				font-size: 28rpx;
				line-height: 50rpx;
				padding: 10rpx 0 15rpx 0;
			}
			
		}
	}
</style>