<template>
	<view class="view-page">
		<view style="margin-left: 10px;">
			<view>
				<text class="u-demo-block__title">订单号</text>
			</view>
			<view>00002023102300000****1012</view>

			<view>
				<text class="u-demo-block__title">设备名称</text>
			</view>
			<view>小推车 ### 型号</view>

			<view class="u-demo-block__title">使用时间</view>
			<view>2023年10月1号13:00:00~2023年10月1号14:00:00</view>

			<view class="u-demo-block__title">地点</view>
			<view>济南国际会展中心一楼西侧</view>

			<view class="u-demo-block__title">状态</view>
			<view>使用中</view>

			<view class="u-demo-block__title">计费</view>
			<view>本次时长1h, 合计计费28￥</view>
		</view>

		<view class="view-button">
			<view class="button-contact">
				<u-button type="info" text="联系售后" @click="customService"></u-button>
			</view>
			<view class="button-submit">
				<u-button type="primary" text="确定归还" :loading="loading" loadingText='设备关闭中,请稍等'
					@click="submit"></u-button>
			</view>
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
			customService(){
				uni.makePhoneCall({phoneNumber: '400-000-0001'})
			},
			submit() {
				this.loading = true
				setTimeout(() => {
					this.showToast({
						type: 'success',
						message: "设备JN0001关锁成功",
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
		display: flex;
		flex-wrap: nowrap;
		margin-top: 120px;
		width: 100%;
	}

	.button-contact {
		width: 35%;
		padding: 3px;
	}

	.button-submit {
		width: 65%;
		padding: 3px;
	}
</style>