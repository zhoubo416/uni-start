<template>
	<view class="u-page">
		<u-list @scrolltolower="scrolltolower">
			<u-list-item>
				<u-cell :isLink="true" arrow-direction="right" @click="toDetail">
					<template #title>
						<view style="display: flex;">
							支付信息<view style="font-size: 0.8rem;color:  goldenrod;">&nbsp; 已读</view>
						</view>
					</template>
					<template #label>
						<view style="font-size: 0.8rem;color: darkgray;"> 
						订单号：20231000000001
						</view>
						<view style="display: flex;justify-content:space-between">
							<view style="font-size: 0.8rem;color:  goldenrod;">
								  设备已归还，本次计费:28.00元
							</view>
						</view>
					</template>
				</u-cell>
			</u-list-item>
			<u-list-item>
				<u-cell :isLink="true" arrow-direction="right" @click="toDetail">
					<template #title>
						<view style="display: flex;">
							订单信息<view style="font-size: 0.8rem;color:  goldenrod;">&nbsp;  未读</view>
						</view>
					</template>
					<template #label>
						<view style="font-size: 0.8rem;color: darkgray;"> 
						设备***已租用
						</view>
						<view style="display: flex;justify-content:space-between">
							<view style="font-size: 0.8rem;color:  red;">
								 使用中...
							</view>
						</view>
					</template>
				</u-cell>
			</u-list-item>
			<u-list-item>
				<u-cell :isLink="true" arrow-direction="right" @click="toDetail">
					<template #title>
						<view style="display: flex;">
							系统通知<view style="font-size: 0.8rem;color:  goldenrod;">&nbsp;  未读</view>
						</view>
					</template>
					<template #label>
						<view style="font-size: 0.8rem;color: darkgray;"> 
						你有一台设备长期未归还，请确认
						</view>
					</template>
				</u-cell>
			</u-list-item>
		</u-list>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				indexList: [],
			}
		},
		onLoad() {
			this.loadmore()
		},
		methods: {
			toDetail() {
				uni.navigateTo({
					url: "/pages/grid/child/child"
				})
			},
			scrolltolower() {
				this.loadmore()
			},
			loadmore() {
				
			}
		},
	}
</script>
<style scoped>
	.u-page{
		padding: 5rpx;
	}
</style>