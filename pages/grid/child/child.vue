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
			<view>设备已归还</view>
			
			<view class="u-demo-block__title">计费</view>
			<view>本次时长1h, 合计计费28￥，已付款</view>
		</view>
		
		<view class="view-button">
			<u-button type="primary" text="联系售后"></u-button>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style scoped>
	.view-page{
		padding: 5px;
		margin-top: 10px;
	}
	.u-demo-block__title {
		color: #8f9ca2;
		margin-top: 8px;
		display: flex;
		flex-direction: row;
	}
	.view-button{
		margin-top: 120px;
		width: 100%;
	}
</style>