<template>
	<view class="container">
		
		<!-- 顶部标题栏 -->
		<view class="header">
			<view class="title">书果星球万达CBD店</view>
			<view class="icons">
				<image class="switch-icon" src="@/static/切图 6.png"></image>
			</view>
		</view>

		<!-- 统计信息 -->
		<view class="stats">
			<view class="stat-item">
				<text class="stat-number">5</text>
				<text class="stat-label">课程延期提醒</text>
			</view>
			<view class="stat-item">
				<text class="stat-number">2</text>
				<text class="stat-label">约课延</text>
			</view>
		</view>

		<!-- 教务中心 -->
		<!-- TODO 后期优化 -->
		<view class="section">
			<view class="section-title">教务中心</view>
			<view class="section-content">
				<view class="grid">
					<view class="grid-item">
						<image class="icon" src="@/static/切图 1.png"></image>
						<text class="grid-label">线索管理</text>
					</view>
					<view class="grid-item">
						<image class="icon" src="@/static/切图 2.png"></image>
						<text class="grid-label">今日待跟进</text>
					</view>
					<view class="grid-item">
						<image class="icon" src="@/static/切图 3.png"></image>
						<text class="grid-label">跟进管理</text>
					</view>
					<view class="grid-item">
						<image class="icon" src="@/static/切图 4.png"></image>
						<text class="grid-label">续课预警</text>
					</view>
					<!-- <view class="grid-item">
						<image class="icon" src="@/static/切图 7.png"></image>
						<text class="grid-label">学员</text>
					</view> -->
				</view>
			</view>
		</view>

	</view>
</template>


<script>
	export default {
		data() {
			return {};
		},
		methods: {}
	};
</script>


<style>
	.container {
		width: 100%;
		height: 100vh;
		/* padding: 10px; */
		background-image: url(@/static/切图 5.png) ;
		background-repeat: no-repeat;
		background-size: contain;
	}

	.header {
		padding-top: 15%;
		padding-left: 40rpx;
		display: flex;
		/* justify-content: space-between; */
		align-items: center;
	}

	.title {
		font-size: 32rpx;
		font-weight: bold;
	}

	.icons { 
		display: flex;
		justify-content: left;
	}

	.switch-icon {
		width: 32rpx;
		height: 32rpx;
		margin-top: 2rpx;
	}

	.stats {
		display: flex;
		justify-content: space-around;
		text-align: center;
		margin-top: 100rpx;
		margin-left: 5%;
		width: 90%;
		height: 160rpx;
		border-radius: 8rpx;
		border: 1rpx solid #ddd;
		background-color: #fff;
		
	}

	.stat-item {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-top: 28rpx;
	}

	.stat-number {
		font-size: 48rpx;
		font-weight: bold;
	}

	.stat-label {
		font-size: 28rpx;
		color: #888;
	}

	.section {
		width: 90%;
		margin-top: 32rpx;
		margin-left: 5%;
		
	}

	.section-title {
		font-size: 32rpx;
		margin-bottom: 32rpx;
	}

	.section-content {
		border: 1rpx solid #ddd;
		padding: 20rpx;
		border-radius: 16rpx;
	}

	.grid {
		display: flex;
		flex-wrap: wrap;
	}

	.grid-item {
		width: 25%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		margin-top: 28rpx;
		margin-bottom: 28rpx;
	}

	.grid-label {
		font-size: 30rpx;
		margin-top: 10rpx;
	}
	
	.icon {
		width: 48rpx;
		height: 48rpx;
		/* margin-left: 20rpx; */
	}

</style>