<template>
	<view class="user-box">
		<view class="info-block">
			<!-- <block>
				<image class="user-logo" src="/static/user.png"></image>
				<view class="user-name">登录</view>
			</block> -->
			<block>
				<image class="user-logo" src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-c14ddd5c-409b-4b8c-8b35-a6267571d0dd/91b60a57-0a25-4e47-8be6-5cfc3f253f19.jpg"></image>
				<view class="user-name">钱包</view>
			</block>
		</view>
		<view class="button-box">
			<view class="button-item">
				<image class="table-icon" src="/static/table.png"></image>
				<view class="table-name">统计分析</view>
			</view>
			<view class="button-item">
				<image class="table-icon" src="/static/more.png"></image>
				<view class="table-name">敬请期待</view>
			</view>
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

<style lang="scss">
@import 'static/css/variable.scss';
page {
	background: #F5F8FD;
}
.info-block {
	width: 100%;
	height: 437rpx;
	background-image: url('https://vkceyugu.cdn.bspapp.com/VKCEYUGU-c14ddd5c-409b-4b8c-8b35-a6267571d0dd/bdfc9661-ab8c-4b4c-b256-f949b0af93a9.png');
	background-size: 100% 100%;
	@include flexCenter;
	flex-direction: column;
	.user-logo {
		width: 120rpx;
		height: 120rpx;
		border-radius: 120rpx;
		margin-top: 25rpx;
	}
	.user-name {
		font-size: 34rpx;
		color: #ffffff;
		font-weight: 500;
		margin-top: 15rpx;
	}

}
.button-box {
	width: 660rpx;
	margin: -60rpx auto 40rpx;
	display: flex;
	justify-content: space-between;
	.button-item {
		width: 310rpx;
		height: 200rpx;
		background: #ffffff;
		border-radius: 10rpx;
		@include flexCenter;
		flex-direction: column;
		.table-icon {
			width: 100rpx;
			height: 100rpx;
		}
		.table-name {
			font-size: 28rpx;
			color: #333333;
			margin-top: 8rpx
		}
	}
}
</style>
