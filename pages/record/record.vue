<template>
	<view class="record">
		<view class="date-box">
			<view class="date-time">2022-08</view>
			<Image class="date-icon" src="/static/date.png"></Image>
		</view>
		<view class="day-box">
			<view  @click="cutArrows" class="day-header">
				<view class="day-name">8月10日</view>
				<Image :class="{'spread-class': spread}" class="date-icon" src="/static/right.png"></Image>
			</view>
			<view :style="{'height': spread ? 132*2+'rpx':'0rpx'}" class="list-box">
				<view class="item-box">
					<view class="record-info">
						<Image src="/static/catering.png" class="item-icon"></Image>
						<view class="name-price">
							<view class="record-name">饮食</view>
							<view class="record-price">￥10.30</view>
						</view>
					</view>
					<view class="item-tools">
						<view class="tools-edit">编辑</view>
						<view class="tools-del">删除</view>
					</view>
				</view>
				<view class="item-box">
					<view class="record-info">
						<Image src="/static/catering.png" class="item-icon"></Image>
						<view class="name-price">
							<view class="record-name">饮食</view>
							<view class="record-price">￥10.30</view>
						</view>
					</view>
					<view class="item-tools">
						<view class="tools-edit">编辑</view>
						<view class="tools-del">删除</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				spread: false
			}
		},
		methods: {
			cutArrows() {
				this.spread = !this.spread
			}
		}
	}
</script>

<style lang="scss">
@import 'static/css/variable.scss';
page {
	background: #F5F8FD;
}
.date-box {
	width: 690rpx;
	margin: 20rpx auto;
	border-radius: 8rpx;
	padding: 20rpx;
	box-sizing: border-box;
	background: #ffffff;
	display: flex;
	justify-content: space-between;
	align-items: center;
	.date-time {
		font-size: 32rpx;
		color: #333333;
	}
	.date-icon {
		width: 48rpx;
		height: 48rpx;
	}
	
}
.day-box {
	width: 690rpx;
	margin: 30rpx auto;
	border-radius: 8rpx;
	overflow: hidden;
	.day-header {
		width: 100%;
		height: 88rpx;
		padding: 20rpx;
		box-sizing: border-box;
		background: $primary-color;
		display: flex;
		align-items: center;
		justify-content: space-between;
		.day-name {
			font-size: 32rpx;
			color: #ffffff;
		}
		.date-icon {
			width: 42rpx;
			height: 42rpx;
			transition: all 0.5s;
		}
		.spread-class {
			transform: rotate(-90deg);
		}
	}
	.list-box {
		background: #ffffff;
		padding: 0rpx 30rpx;
		height: 0px;
		transition: all 0.4s cubic-bezier(0.25, 1, 0.25, 1);
		.item-box {
			padding: 20rpx 0px;
			display: flex;
			align-items: center;
			justify-content: space-between;
			border-bottom: 1px solid #DEE5F1;
			.record-info {
				display: flex;
				.item-icon {
					width: 90rpx;
					height: 90rpx;
					margin-right: 10rpx;
				}
				.name-price {
					display: flex;
					flex-direction: column;
					justify-content: space-between;
					align-items: center;
					.record-name {
						font-size: 28rpx;
					}
					.record-price {
						font-size: 28rpx;
					}
				}
			}
			.item-tools {
				display: flex;
				align-items: center;
				.tools-edit {
					font-size: 28rpx;
					color: #2979ff;
					margin-right: 18rpx
				}
				.tools-del {
					font-size: 28rpx;
					color: #fa3534;
				}
			}
		}
		.item-box:last-child {
			border-bottom: none
		}
	}
}

</style>
