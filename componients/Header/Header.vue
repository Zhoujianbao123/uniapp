<template>
	<view class="header" :style='"height:"+headHeight+"px"'>
		<view class='top'>
			<view class="icons">
				<text class="iconfont icon-geren"></text>
			</view>
			<view class="search"><text class="iconfontTwo icon-search"></text>点击搜索</view>
			<view class="zhanwei"></view>
		</view>

	</view>
</template>

<script>
	export default {
		props: ['headHeight'],
		data() {
			return {}
		},

	}
</script>

<style scoped="scss">
	.iconfontTwo{
		font-family: "iconfont" !important;
		font-size: 16px;
		font-style: normal;
		position:absolute;
		left:10px;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
	}
	.header {
		width: 100%;
		background: #FF5A5F;
		text-align: center;
	}

	.top {
		display: flex;
		height: 100%;
		justify-content: space-between;
		align-items: center;

	}

	.icons {
		flex: 1.5;
		height: 100%;
		font-size: 16px;
		color: #FFFFFF;
		text-align:center;
		line-height:40px;
		/* background: #4CD964; */
	}

	.zhanwei {
		flex: 3;
		height: 100%;
		display: flex;
		align-items: center;
	}

	.search {
		background: #F0F0F0;
		height: 32px;
		line-height:32px;	
		flex: 5;
		position:relative;
		border-radius: 16px;
	}
</style>
