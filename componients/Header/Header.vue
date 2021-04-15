<template>
	<view class="header" :style='"height:"+headHeight+"px"'>
		<view class='top'>
			<view class="icons">
				<text class="iconfont">&#xe61c;</text>
			</view>
			<view class="search"><text class="iconfontTwo">&#xe62a;</text>点击搜索</view>
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
	@font-face {
		font-family: 'iconfont';
		src: url('https://at.alicdn.com/t/font_2486844_kci3mj2ymoa.ttf') format('truetype');
	}

	.iconfont {
		font-family: "iconfont" !important;
		font-size: 32px;
		font-style: normal;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
	}
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
		flex: 1;
		height: 100%;
		font-size: 16px;
		color: #FFFFFF;
		text-align:center;
		line-height:40px;
		/* background: #4CD964; */
	}

	.zhanwei {
		flex: 1;
		height: 100%;
		display: flex;
		align-items: center;
	}

	.search {
		background: #F0F0F0;
		height: 32px;
		line-height:32px;	
		flex: 2;
		position:relative;
		border-radius: 16px;
	}
</style>
