<template>
	<view class="container">
		<!-- 顶部搜索栏和筛选按钮 -->
		<view class="search-bar">
			<input class="search-input uni-input" confirm-type="search" placeholder="名字/手机号" />
			<button class="filter-button">
				<!-- <image src="/static/filter-icon.png"></image> -->
			</button>
		</view>

		<!-- 列表项 -->
		<view class="list-item" v-for="(item, index) in listItems" :key="index">
			<image class="avatar" :src="item.avatar"></image>
			<view class="content">
				<view class="header">
					<text class="name">{{ item.name }}</text>
					<view class="status">{{ item.status }}</view>
					<view class="follow-status">{{ item.followStatus }}</view>
				</view>
				<view class="details">
					<text>学生来源: {{ item.source }}</text>
					<text>最后跟进时间: {{ item.lastFollowTime }}</text>
				</view>
			</view>
		</view>
		
		<view class="endline">
			-----  我是底！我是底啊！  -----
		</view>

		<!-- 右下角添加按钮 -->
		<button class="add-button" />
	</view>
</template>

<script>
	export default {
		data() {
			return {
				listItems: [{
						avatar: '/static/avatar1.png',
						name: '王瑞琛',
						status: '高',
						followStatus: '未分配',
						source: '门店咨询',
						lastFollowTime: '2024-04-12 08:11'
					},
					{
						avatar: '/static/avatar2.png',
						name: '王瑞琛',
						status: '中',
						followStatus: '未分配',
						source: '公开作业',
						lastFollowTime: '2024-04-12 08:11'
					},
					{
						avatar: '/static/avatar3.png',
						name: '王瑞琛',
						status: '低',
						followStatus: '跟进中',
						source: '门店咨询',
						lastFollowTime: '2024-04-12 08:11'
					},
					{
						avatar: '/static/avatar4.png',
						name: '王瑞琛',
						status: '低',
						followStatus: '待跟进',
						source: '柿子老师',
						lastFollowTime: '2024-04-12 08:11'
					},
					{
						avatar: '/static/avatar4.png',
						name: '王瑞琛',
						status: '低',
						followStatus: '待跟进',
						source: '柿子老师',
						lastFollowTime: '2024-04-12 08:11'
					},
					{
						avatar: '/static/avatar4.png',
						name: '王瑞琛',
						status: '低',
						followStatus: '待跟进',
						source: '柿子老师',
						lastFollowTime: '2024-04-12 08:11'
					},
					{
						avatar: '/static/avatar4.png',
						name: '王瑞琛',
						status: '低',
						followStatus: '待跟进',
						source: '柿子老师',
						lastFollowTime: '2024-04-12 08:11'
					},
					{
						avatar: '/static/avatar4.png',
						name: '王瑞琛',
						status: '低',
						followStatus: '待跟进',
						source: '柿子老师',
						lastFollowTime: '2024-04-12 08:11'
					},
					{
						avatar: '/static/avatar4.png',
						name: '王瑞琛',
						status: '低',
						followStatus: '待跟进',
						source: '柿子老师',
						lastFollowTime: '2024-04-12 08:11'
					},
					{
						avatar: '/static/avatar4.png',
						name: '王瑞琛',
						status: '低',
						followStatus: '待跟进',
						source: '柿子老师',
						lastFollowTime: '2024-04-12 08:11'
					},
					{
						avatar: '/static/avatar5.png',
						name: '王瑞琛',
						status: '低',
						followStatus: '已成交',
						source: '柿子老师',
						lastFollowTime: '2024-04-12 08:11'
					}
				]
			};
		}
	};
</script>

<style>
	.container {
		display: flex;
		flex-direction: column;
		background-color: #fff;
	}

	.search-bar {
		display: flex;
		align-items: center;
		padding: 0 36rpx;
		background-color: #fff;
		margin-bottom: 14rpx;
	}

	.search-input {
		flex: 1;
		border: none;
		outline: none;
		padding: 5rpx;
		width: 70%;
		height: 80rpx;
		border-radius: 8px;
		opacity: 0.8;
		
		background: #F7F7F9;
	}

	.filter-button {
		background: none;
		border: none;
		padding: 5px;
	}

	.list-item {
		display: flex;
		align-items: center;
		background-color: #fff;
		height: 200rpx;
		padding: 0 36rpx;
		border-width: 0px 0px 1rpx 0px;
		border-style: solid;
		border-color: rgba(230, 229, 231, 0.8);
	}

	.avatar {
		width: 120rpx;
		height: 120rpx;
		border-radius: 50%;
		background-color: aqua;
	}

	.content {
		flex: 1;
		margin-left: 36rpx;
	}

	.header {
		display: flex;
		align-items: center;
		margin-bottom: 10rpx;
	}

	.name {
		font-size: 40rpx;
		/* font-weight: 600; */
		font-family: 苹方-简;
	}

	.status {
		margin-left: 24rpx;
		margin-top: 5rpx;
		padding: 3rpx 5rpx 4rpx;
		font-size: 26rpx;
		color: #fff;
		border-radius: 6rpx;
		background-color: #ff6b6b;
	}

	.follow-status {
		margin-left: auto;
		color: #ff6b6b;
		/* 根据实际颜色调整 */
	}

	.details {
		display: flex;
		flex-direction: column;
	}

	.details text {
		font-size: 28rpx;
		color: #3D3D3D;
		margin-top: 4rpx;
		opacity: 0.7;
	}
	
	.endline  {
		text-align: center;
		margin-top: 180rpx;
		margin-bottom: 120rpx;
		font-size: 26rpx;
		color: #3D3D3D;
		opacity: 0.5;
	}

	.add-button {
		position: fixed;
		bottom: 200rpx;
		right: 100rpx;
		width: 120rpx;
		height: 120rpx;
		background-color: #ff6b6b;
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
		box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
		background-image: url(@/static/add-button.png);
		background-repeat: no-repeat;
		background-size: contain;
	}
	
	.add-text {
		font-size: 80rpx;
		color: #fff;
	}
</style>