<template>
	<view class="container">
		<!-- 头像和用户名部分 -->
		<view class="header">
			<image class="avatar" src="/static/avatar.png"></image>
			<view class="user-info">
				<view class="username">
					<text>老师名称</text>
					<image class="tag" src="@/static/切图 8.png"></image>
				</view>
				<text class="organization">培训机构名称</text>
			</view>
		</view>

		<!-- 教务中心 -->
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
					<view class="grid-item">
						<image class="icon" src="@/static/切图 7.png"></image>
						<text class="grid-label">学员</text>
					</view>
				</view>
			</view>
		</view>
		

		<!-- 其他 -->
		<view class="section">
			<view class="section-title">其他</view>
			<view class="section-content">
				<view class="grid">
					<view class="grid-item">
						<image class="icon" src="@/static/切图 9.png"></image>
						<text class="grid-label">设置</text>
					</view>
					<view class="grid-item">
						<image class="icon" src="@/static/切图 10.png"></image>
						<text class="grid-label">切换身份</text>
					</view>
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
		display: flex;
		flex-direction: column;
		height: 100vh;
	}

	.header {
		display: flex;
		align-items: center;
		margin-bottom: 40rpx;
		margin-top: 40rpx;
		margin-left: 36rpx;
	}

	.avatar {
		width: 120rpx;
		height: 120rpx;
		border-radius: 50%;
		background-color: aqua;
		margin-right: 12rpx;
	}

	.user-info {
		display: flex;
		flex-direction: column;
		margin-left: 16rpx;
	}

	.username {
		display: flex;
		align-items: center;
	}

	.username text {
		font-size: 36rpx;
	}

	.tag {
		margin-left: 20rpx;
		width: 174rpx;
		height: 48rpx;
	}

	.organization {
		margin-top: 15rpx;
		font-size: 28rpx;
		font-weight: 300;
		color: #666;
	}

	.section {
		margin-top: 54rpx;
		
	}
	
	.section-title {
		width: 25%;
		font-size: 32rpx;
		margin-bottom: 10rpx;
		text-align: center;
	}
	
	.section-content {
		
	}
	
	.grid {
		display: flex;
		flex-wrap: wrap;
		width: 100%;
	}
	
	.grid-item {
		width: 25%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		margin-top: 32rpx;
	}
	
	.grid-label {
		/* display: block; */
		font-size: 32rpx;
		margin-top: 10rpx;
	}
	
	.icon {
		width: 48rpx;
		height: 48rpx;
		/* margin-left: 20rpx; */
	}
	
</style>