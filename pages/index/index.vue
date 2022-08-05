<template>
	<view class="content">
		<view class="select-list">
			<swiper class="swiper" indicator-dots indicator-color="#c4c6c9" indicator-active-color="#f9ae3d">
				<swiper-item v-for="swiperItem in list" :key="swiperItem.key">
					<view class="swiper-item">
						<view class="item-box" v-for="item in swiperItem.data" :key="item.key" @click="selectFun(item)">
							<view class="item-main" :class="{'item-active': activeKey==item.key}">
								<image :src="item.src" class="select-icon"></image>
								<view class="select-name">{{item.name}}</view>
							</view>
						</view>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<view class="keyboard-box">
			<view class="money-label">￥10.30</view>
			<view class="row-box">
				<view class="number-box">
					<view class="number-item">1</view>
					<view class="number-item">2</view>
					<view class="number-item">3</view>
					<view class="number-item">4</view>
					<view class="number-item">5</view>
					<view class="number-item">6</view>
					<view class="number-item">7</view>
					<view class="number-item">8</view>
					<view class="number-item">9</view>
					<view class="number-item" style="margin-bottom:0px">.</view>
					<view class="number-item" style="margin-bottom:0px">0</view>
					<view class="number-item" style="margin-bottom:0px">
						<image src="/static/del.png" style="width: 50rpx;height: 50rpx;"></image>
					</view>
				</view>
				<view class="tool-box">
					<view class="tool-date">
						<image src="/static/date.png" class="date-icon"></image>
						<view class="date-label">今天</view>
					</view>
					<view class="tool-add-btn">添加</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	let swiper_1 = [
		{ name: "餐饮", src: "/static/catering.png", key: "catering"},
		{ name: "购物", src: "/static/shopping.png", key: "shopping"},
		{ name: "日用", src: "/static/daily.png", key: "daily"},
		{ name: "交通", src: "/static/traffic.png", key: "traffic"},
		{ name: "蔬菜", src: "/static/vegetable.png", key: "vegetable"},
		{ name: "水果", src: "/static/fruits.png", key: "fruits"},
		{ name: "零食", src: "/static/snacks.png", key: "snacks"},
		{ name: "运动", src: "/static/exercise.png", key: "exercise"},
		{ name: "娱乐", src: "/static/recreation.png", key: "recreation"},
		{ name: "通讯", src: "/static/message.png", key: "message"},
		{ name: "服饰", src: "/static/costume.png", key: "costume"},
		{ name: "美容", src: "/static/hairdressing.png", key: "hairdressing"},
		{ name: "住房", src: "/static/housing.png", key: "housing"},
		{ name: "家庭", src: "/static/family.png", key: "family"},
		{ name: "社交", src: "/static/contact.png", key: "contact"},
		{ name: "旅行", src: "/static/travel.png", key: "travel"},
	]
	let swiper_2 = [
		{ name: "烟酒", src: "/static/tobacco.png", key: "tobacco"},
		{ name: "数码", src: "/static/numericalCode.png", key: "numericalCode"},
		{ name: "汽车", src: "/static/car.png", key: "car"},
		{ name: "医疗", src: "/static/medical.png", key: "medical"},
		{ name: "书籍", src: "/static/books.png", key: "books"},
		{ name: "学习", src: "/static/study.png", key: "study"},
		{ name: "宠物", src: "/static/pet.png", key: "pet"},
		{ name: "礼金", src: "/static/gifts.png", key: "gifts"},
		{ name: "礼品", src: "/static/present.png", key: "present"},
		{ name: "办公", src: "/static/work.png", key: "work"},
		{ name: "维修", src: "/static/service.png", key: "service"},
		{ name: "捐赠", src: "/static/donate.png", key: "donate"},
		{ name: "彩票", src: "/static/lottery.png", key: "lottery"},
		{ name: "红包", src: "/static/redPacket.png", key: "redPacket"},
		{ name: "快递", src: "/static/expressage.png", key: "expressage"},
		{ name: "其他", src: "/static/else.png", key: "else"},
	]
	let swiper_3 = [
		{ name: "还款", src: "/static/refund.png", key: "refund"},
		{ name: "借出", src: "/static/lend.png", key: "lend"},
		{ name: "饮品", src: "/static/drink.png", key: "drink"},
		{ name: "游戏", src: "/static/game.png", key: "game"},
	]
	export default {
		data() {
			return {
				list: [{
						key: "swiper-item-1",
						data: swiper_1
					}, 
					{
						key: "swiper-item-2",
						data: swiper_2
					}, 
					{
						key: "swiper-item-3",
						data: swiper_3
					}
				],
				activeKey: "catering"
			}
		},
		onLoad() {

		},
		methods: {
			selectFun(item) {
				this.activeKey = item.key
			}
		}
	}
</script>

<style lang="scss">
@import 'static/css/variable.scss';
.content {
	height: 100vh;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	.select-list {
		width: 100%;
		height: calc(100vh - 480rpx);
		.swiper {
			width: 100%;
			height: 100%;
			
			.swiper-item {
				width: 100%;
				height: 100%;
				box-sizing: border-box;
				padding: 20rpx 20rpx 50rpx;
				display: flex;
				flex-wrap: wrap;
				.item-box {
					width: 177rpx;
					height: 130rpx;
					display: flex;
					align-items: center;
					justify-content: center;
					.item-main {
						width: 120rpx;
						height: 120rpx;
						border-radius: 10rpx;
						border: 1px solid #999999;
						display: flex;
						flex-direction: column;
						justify-content: center;
						align-items: center;
						transition: all .3s;
						.select-icon {
							width: 75rpx;
							height: 75rpx;
						}
						.select-name {
							font-size: 22rpx;
							margin-top: 5rpx;
							transition: all .3s;
						}
					}
					.item-active {
						border-color: $primary-color;
						.select-name {
							color: $primary-color
						}
					}
				}
			}
		}
	}
	.keyboard-box {
		width: 100%;
		height: 478rpx;
		box-sizing: border-box;
		padding: 0px 20rpx 20rpx;
		.money-label {
			padding: 20rpx;
			border-radius: 10rpx;
			border: 1px solid $primary-color;
			font-size: 32rpx;
			color: $primary-color
		}
		.row-box {
			width: 100%;
			height: 350rpx;
			margin-top: 20rpx;
			display: flex;
			justify-content: space-between;
			.number-box {
				flex: 1;
				height: 100%;
				display: flex;
				flex-wrap: wrap;
				.number-item {
					width: 160rpx;
					height: 70rpx;
					border-radius: 10rpx;
					border: 1px solid $primary-color;
					@include flexCenter;
					color: $primary-color;
					font-size: 28rpx;
					margin-bottom: 15rpx;
				}
				.number-item:nth-child(3n-1) {
					margin-left: 30rpx;
					margin-right: 30rpx;
				}
			}
			.tool-box {
				width: 130rpx;
				height: 100%;
				margin-left: 20rpx;
				display: flex;
				flex-direction: column;
				justify-content: space-between;
				.tool-date {
					flex: 1;
					@include flexCenter;
					flex-direction: column;
					box-shadow: 1px 1px 3px 0px #c4c6c9;
					border-radius: 10rpx;
					.date-icon {
						width: 40rpx;
						height: 40rpx;
						margin-bottom: 8rpx;
					}
					.date-label {
						font-size: 28rpx;
						color: $primary-color;
					}
				}
				.tool-add-btn {
					flex: 1;
					@include flexCenter;
					margin-top: 20rpx;
					background: $primary-color;
					font-size: 28rpx;
					color: #ffffff;
					border-radius: 10rpx;
				}
			}
		}
	}
	
}

</style>
