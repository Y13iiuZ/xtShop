<template>
	<view class="goodsColor">
		<goods @laile='shoudo' :god='god' ref="controlFather" @woyoulaile='goGoods'></goods> <!-- 通过ref属性获取子组件实例-->
		<view class="shows" v-if="flag">----------到底了---------- </view>
	</view>
</template>

<script>
	import Goods from '../components/good-list/goods-list.vue'
	export default {
		components:{
			Goods
		},
		data() {
			return {
				god:[],
				flag:false
			}
		},
		methods: {
			shoudo(arrays){
				this.god = arrays
				// console.log(this.god)
				uni.stopPullDownRefresh()/* 实际开发中 要利用回调函数获取 */
			},
			goGoods(){
				uni.navigateTo({
					url:'/pages/goods-detail/goods-detail'
				})
			}
		},
		onReachBottom() {
			if(this.god.length < 13) return this.flag = true
			console.log('触及底线了')
			// let copyGod = this.god.slice()
			// this.god = [...this.god,...copyGod]
			console.log(this.god)
		},
		onPullDownRefresh() {
			console.log('刷新页面了')
			this.god = []
			// console.log(this.god)
			this.flag = false
			setTimeout(()=>{
				this.$refs['controlFather'].hei() //父控子
			},500)
		}
	}
</script>

<style lang="scss">
	.goodsColor {
		background-color: #BBFFFF;
		.shows {
			width: 100%;
			height: 50px;
			line-height: 50px;
			// background-color: #fff;
			font-size: 28rpx;
			text-align: center;
		}
	}

</style>
