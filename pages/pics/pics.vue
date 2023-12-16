<template>
	<view class="pics">
		<scroll-view class="left" scroll-y>
			<view :class="active===index ? 'active' : ''" v-for="(item,index) in lists" :key="index" @click="dj(index,item.id)">{{item.names}}</view>
		</scroll-view>
		
		<scroll-view class="right" scroll-y>
			<view v-for="items in oldpicList" :key="items.id" class="itemPic">
				<image :src="items.picSrc" @click="previewPic(items.picSrc)"></image>
				<text>{{items.text}}</text>
			</view>
			<view v-if="this.oldpicList.length === 0">暂无数据</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				lists:[
					{id:1,names:'家具生活'},
					{id:2,names:'超市便利'},
					{id:3,names:'新鲜果蔬'},
					{id:4,names:'美团买药'},
					{id:5,names:'社区信息'},
					{id:6,names:'社区随机拍'},
					{id:7,names:'和谐一家亲'},
					{id:8,names:'家具生活'},
					{id:9,names:'超市便利'},
					{id:10,names:'新鲜果蔬'},
					{id:11,names:'美团买药'},
					{id:12,names:'社区信息'},
					{id:13,names:'社区随机拍'},
					{id:14,names:'和谐一家亲'},
				],
				active:0,
				picList:[
					{
						id:1,
						picSrc:'http://gd-hbimg.huaban.com/428cb9d7ae53f4cbfe37e40134ad176512993adf2cde6-0DtsGN',
						text:'海尔Haier晒宝贝赢好礼'
					},
					{
						id:1,
						picSrc:'https://i01piccdn.sogoucdn.com/6f6c5ad5a9b4e70b',
						text:'青山绿水好阳光'
					},
					{
						id:1,
						picSrc:'http://youimg1.c-ctrip.com/target/fd/tg/g1/M0A/C9/EE/CghzflTZheuAclC5ACtkBKSrYcA894.jpg',
						text:'hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh'
					},
					{
						id:2,
						picSrc:'http://gd-hbimg.huaban.com/428cb9d7ae53f4cbfe37e40134ad176512993adf2cde6-0DtsGN',
						text:'hhhhhhhhhhhhhhhhhh第二个hhhhhhhhhhhh'
					},
					{
						id:3,
						picSrc:'http://gd-hbimg.huaban.com/428cb9d7ae53f4cbfe37e40134ad176512993adf2cde6-0DtsGN',
						text:'这是我的小家园'
					}
				],
				oldpicList:[]
			}
		},
		methods: {
			dj(i,id){//1,2
				this.active = i;
				var demo = this.picList.filter(res=>{
					return res.id === id
				})
				// console.log(demo)
				this.oldpicList = demo
			},
			previewPic(current){
				const urll = this.oldpicList.map(res=>{
					return res.picSrc
				})
				uni.previewImage({
					current,
					urls:urll
				})
			}
		},
		onLoad() {
			this.dj(0,this.picList[0].id)
		}
	}
</script>

<style lang="scss">
page {
	height: 100%;
}
.pics {
	height: 100%;
	display: flex;
	.left {
		width: 200rpx;
		height: 100%;
		border-right: 1px solid #FDF5E6;
		view {
			height: 60px;
			line-height: 60px;
			color: #FF7F24;
			text-align: center;
			font-size: 30rpx;
			border-top: 1px solid #FDF5E6;
		}
		.active {
			background: #FFE4B5;
			color: #fff;
		}
	}
	.right {
		height: 100%;
		width: 540rpx;
		margin: 10rpx auto;
		.itemPic {
			image {
				width:540rpx;
				height: 540rpx;
				border-radius: 5px;
			}
			text {
				font-size: 30rpx;
				line-height: 60rpx;
				word-break: break-all;//二选一
				// word-wrap: break-word;
			}
		}
	}
}
</style>
