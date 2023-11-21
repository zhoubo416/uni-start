<template>
	<view class="u-page">
		<u-list @scrolltolower="scrolltolower">
			<u-list-item v-for="(item, index) in indexList" :key="index">
				<template v-if='index === 0'>
					<u-cell :title="`设备-${index + 1}`" :isLink="true" arrow-direction="right" @click="toDetail">
						<template #icon>
							<u-avatar shape="square" size="35" :src="item.url"
								customStyle="margin: -3px 5px -3px 0"></u-avatar>
						</template>
						<template #label>
							<view style="font-size: 0.8rem;color: darkgray;"> 
							 开始时间：2023-10-{{index}} 13:00
							</view>
							<view style="display: flex;justify-content:space-between">
								<view style="font-size: 0.8rem;color:  red;">
									 使用中...
								</view>
								<view style="margin-right: 20px;">
									<u-icon name="chat" label="联系售后" labelSize="0.8rem" labelColor='goldenrod'></u-icon>
								</view>
							</view>
						</template>
					</u-cell>
				</template>
				<template v-else>
					<u-cell :title="`设备-${index + 1}`" :isLink="true" arrow-direction="right" @click="toDetail">
						<template #icon>
							<u-avatar shape="square" size="35" :src="item.url"
								customStyle="margin: -3px 5px -3px 0"></u-avatar>
						</template>
						<template #label>
							<view style="font-size: 0.8rem;color: darkgray;"> 2023-10-{{index}} 13:00~2023-10-{{index}}
								14:00
								共1小时
							</view>
							<view style="display: flex;justify-content:space-between">
								<view style="font-size: 0.8rem;color:  goldenrod;">
									 已归还，本次计费:28.00元
								</view>
								<view style="margin-right: 20px;">
									<u-icon name="chat" label="联系售后" labelSize="0.8rem" labelColor='goldenrod'></u-icon>
								</view>
							</view>
						</template>
					</u-cell>
				</template>
				
			</u-list-item>
		</u-list>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				indexList: [],
				urls: [
					'https://cdn.uviewui.com/uview/album/1.jpg',
					'https://cdn.uviewui.com/uview/album/2.jpg',
					'https://cdn.uviewui.com/uview/album/3.jpg',
					'https://cdn.uviewui.com/uview/album/4.jpg',
					'https://cdn.uviewui.com/uview/album/5.jpg',
					'https://cdn.uviewui.com/uview/album/6.jpg',
					'https://cdn.uviewui.com/uview/album/7.jpg',
					'https://cdn.uviewui.com/uview/album/8.jpg',
					'https://cdn.uviewui.com/uview/album/9.jpg',
					'https://cdn.uviewui.com/uview/album/10.jpg',
				]
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
				for (let i = 0; i < 30; i++) {
					this.indexList.push({
						url: this.urls[uni.$u.random(0, this.urls.length - 1)]
					})
				}
			}
		},
	}
</script>
<style scoped>
	.u-page{
		padding: 5rpx;
	}
</style>