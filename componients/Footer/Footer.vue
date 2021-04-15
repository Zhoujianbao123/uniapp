<template>
	<view class="footer">
		<view v-for="(item,index) in tabList" :key="index">
			<view class="navigator" :class="currentTabIndex===index?'hello':'welcome'" @tap="switchTab(index)">
				<view class="icon">
					<text class="iconfont"		
					:class="item.icon"
						></text>
					<!-- <text v-if="item.badge" class="uni_badge">{{item.badge}}</text>
					<text v-if="item.badgeDot" class="uni_badge uni_badge_dot">{{item.badge}}</text> -->
				</view>
				<view class="text">
					{{item.text}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			current: {
				type: [Number, String],
				default: 0
			}
		},
		data() {
			return {
				tabList: [{
						icon:'icon-shouye' ,
						text: '首页',
						badge: 1
					},
					{
						icon:'icon-liebiao1',
						text: '购物中心',
						badge: 1
					},
					{
						icon: 'icon-gouwuche',
						text: '购物车',
						badge: 1
					},
					{
						icon: 'icon-geren',
						text: '我的',
						badge: 1
					}
				],
				currentTabIndex: this.current
			}
		},
		methods: {
			switchTab(index) {
				this.currentTabIndex = index
				this.$emit('click', index)
			}
		}
	}
</script>

<style scoped>
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
	.hello{
		color:#FF5A5F;
	}
	.welcome{
		color:#F0AD4E;
	}
	.footer {
		display: flex;
		justify-content: space-between;
		align-items: center;
		position:fixed;
		width:100%;
		left:0;
		bottom:0;
	}
	.navigator{
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
</style>
