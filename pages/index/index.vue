<template>
	<view class="container" :style='phoneHeight'>

		<Header :headHeight="headHeight"></Header>

	</view>
</template>

<script>
	import Header from "@/componients/Header/Header"
	export default {
		data() {
			return {
				phoneHeight:'',
				phoneHeightTwo:null,
				menuButtonInfo:'',
				headHeight:'',
				//胶囊的高度	
			}
		},
		components: {
			Header
		},
		onReady(){
			this.getPhoneHeight();
			this.getMenuBotton()
			this.getHeadHeight()
			// console.log(this.phoneHeight)
		},
		methods: {
			//获取手机状态栏的宽度
			getPhoneHeight(){
				let that=this
				uni.getSystemInfo({
					success(res) {
						console.log(res)
						that.phoneHeight=`margin-top:${res.statusBarHeight}px`
						that.phoneHeightTwo=res.statusBarHeight
						console.log(that.phoneHeightTwo)
					}
				})
			},
			//获取胶囊的位置，高度，宽度
			getMenuBotton(){
				this.menuButtonInfo=uni.getMenuButtonBoundingClientRect()
				console.log(this.menuButtonInfo,'胶囊信息')
			},
			//获取头部布局高度
			getHeadHeight(){
				this.headHeight=(this.menuButtonInfo.bottom-this.menuButtonInfo.height-this.phoneHeightTwo)*2+this.menuButtonInfo.height
							console.log(this.headHeight)
			}
			
		}
	}
</script>

<style>
	.container {
		/* width:100%; */
	}
</style>
