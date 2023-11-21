<template>
	<view class="view-page">
		<view style="margin-left: 10px;">

			<view>
				<text class="u-demo-block__title">设备名称</text>
			</view>
			<view>小推车 ### 型号</view>

			<view>
				<text class="u-demo-block__title">设备编号</text>
			</view>
			<view>JN00001</view>

			<view class="u-demo-block__title">地点</view>
			<view>济南国际会展中心一楼西侧</view>

			<view class="u-demo-block__title">计费</view>
			<view>20￥/h</view>
		</view>

		<view class="view-button">
			<u-button type="primary" text="确定租用" :loading='loading' loadingText='设备打开中,请稍等' @click="open"></u-button>
		</view>
		<u-toast ref="uToast"></u-toast>


	</view>
</template>

<script>
	export default {
		data() {
			return {
				loading: false
			}
		},
		methods: {
			showToast(params) {
				this.$refs.uToast.show({
					...params,
					complete() {
						params.url && uni.navigateTo({
							url: params.url
						})
					}
				})
			},
			open() {
				this.loading = true
				setTimeout(() => {
					this.showToast({
						type: 'success',
						message: "设备 JN0001开锁成功",
						iconUrl: 'https://cdn.uviewui.com/uview/demo/toast/success.png'
					});
					this.loading = false
					uni.switchTab({
						url: '/pages/list/list'
					});
				}, 2000)
			}
		}
	}
</script>

<style scoped>
	.view-page {
		padding: 5px;
		margin-top: 10px;
	}

	.u-demo-block__title {
		color: #8f9ca2;
		margin-top: 8px;
		display: flex;
		flex-direction: row;
	}

	.view-button {
		margin-top: 120px;
		width: 100%;
	}
</style>