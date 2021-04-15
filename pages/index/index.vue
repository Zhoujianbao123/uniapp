<template>
	<view class="container" :style='phoneHeight'>	
		<view>
			<Header :headHeight="headHeight"></Header>
		</view>
		<view class="content"></view>
		<view class="tabbar">
			<Footer :current="currentTabIndex" @click="tabClick"></Footer>
		</view>	
		
	</view>
</template>

<script>
	import Header from "@/componients/Header/Header"
	import Footer from "@/componients/Footer/Footer"
	export default {
		data() {
			return {
				//当前tabbar
				currentTabIndex:1,
				phoneHeight:'',
				phoneHeightTwo:null,
				menuButtonInfo:'',
				headHeight:'',
				//胶囊的高度	
			}
		},
		components: {
			Header,
			Footer
		},
		onReady(){
			this.getPhoneHeight();
			this.getMenuBotton()
			this.getHeadHeight()
			// console.log(this.phoneHeight)
		},
		methods: {
			//点击当前tabbar索引
			tabClick(index){
				console.log("当前索引"+index)
				this.currentTabIndex=index
			},
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
		width:100%;
		height:100%;
		overflow: hidden;
	}
	
</style>
